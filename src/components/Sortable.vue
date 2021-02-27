<template>
  <div class="screen_only">
    <input type="search" placeholder="検索" v-model="searchWord" @keydown.enter="send">
    <select v-model="sortKey" @change="sort">
      <option>ソート順</option>
      <option value="ym">時期</option>
      <option value="scale">規模</option>
    </select>
  </div>
</template>

<script>
export default {
  data(){
    return {
      searchWord: "",
      sortKey: ""
    }
  },
  methods: {
    send(event){
      // 日本語入力中のEnterは無視する
      if (event.keyCode !== 13) return;

      this.$emit("search", this.searchWord);
    },
    sort(){
      this.$emit("sort", this.sortKey)
    }
  }
}
</script>