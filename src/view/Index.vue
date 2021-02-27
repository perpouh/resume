<template>
  <article>
    <h1>職務経歴書</h1>
    <section>
      <h2>自己PR</h2>
      <div v-html="nl2br(resume.summary)"></div>
    </section>
    <section>
      <h2>技術スタック</h2>
      <h3>OS</h3>
      {{resume.skill.os.join(',')}}
      <h3>言語/フレームワーク</h3>
      {{resume.skill.language_framework.join(',')}}
      <h3>ミドルウェア</h3>
      {{resume.skill.middleware.join(',')}}
      <h3>ツール</h3>
      {{resume.skill.tools.join(',')}}
    </section>
    <section>
      <sortable @search="refine" @sort="sort"></sortable>
    </section>
    <section>
      <carrer-table v-for="carrer in disp_carrer" :key="carrer.no" :carrer="carrer"></carrer-table>
      <p v-if="!disp_carrer">検索結果はありません。</p>
    </section>
  </article>
</template>

<script>
import CarrerTable from '../components/CarrerTable'
import Sortable from '../components/Sortable'
import resume from '../resume.json'
export default {
  data(){
    return {
      resume: resume,
      disp_carrer: resume.carrer
    }
  },
  components: {
    CarrerTable,
    Sortable
  },
  methods: {
    nl2br(text){
      return text.replace(/\n/g,'<br/>')
    },
    refine(word){
      // あまりちゃんと考えていない
      if(typeof word != "string") return;
      this.disp_carrer = resume.carrer.filter(function(carrer){
        if(carrer.summary.search(word) > 0) return true;
        if(carrer.role.search(word) > 0) return true;
        if(carrer.phase_in_charge.search(word) > 0) return true;
        if(carrer.business_content.join('').search(word) > 0) return true;
        if(carrer.achievement.search(word) > 0) return true;
        if(carrer.development_environment.join('').search(word) > 0) return true;
        return false;
      });
    },
    sort(sortKey){
      this.disp_carrer = this.disp_carrer.sort(function(a, b){
        // 規模のところがStringなのでもうちょっと考えないとだめ
        if(a[sortKey] > b[sortKey])return 1
        if(a[sortKey] < b[sortKey])return -1
        return 0
      })
    }
  } 
}
</script>