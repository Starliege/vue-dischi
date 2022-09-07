<template>
    <section>
      <AlbumList />
    </section>
  </template>
  
  <script>
import AlbumList from "../section/AlbumList.vue";
  
  export default {
    name: "PageMain",
    components: {
    AlbumList
},
  };
  </script>
  
  <style lang="scss" scoped>
  @import "../../assets/style/globals.scss";
  
  section {
    background: $second-color;
    min-height: calc(100vh - 124px);
  }
  </style>