<template>
  <article>
    <section>
      <carrer-table v-for="carrer in resume.carrer" :key="carrer.no" :carrer="carrer"></carrer-table>
    </section>
  </article>
</template>

<script>
import CarrerTable from '../components/CarrerTable'
import resume from '../resume.json'
export default {
  data(){
    return {
      resume: resume
    }
  },
  components: {
    CarrerTable
  }
}
</script>