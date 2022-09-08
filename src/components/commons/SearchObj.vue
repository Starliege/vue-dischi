<template>
    <div class="search">
      <label>Filtra per genere</label>
      <select @change="$emit('search', selected)" v-model="selected">
        <option value="">Tutti</option>
        <option v-for="(genre, index) in genreArr" :key="index" :value="genre">
          {{ genre }}
        </option>
      </select>
    </div>
  </template>
  
  <script>
  export default {
    name: "SearchObj",
    props: {
      albumArr: Array,
    },
    data() {
      return {
        genreArr: [],
        selected: "",
      };
    },
    methods: {
      genreList() {
        this.albumArr.forEach((album) => {
          if (!this.genreArr.includes(album.genre)) {
            this.genreArr.push(album.genre);
          }
        });
      },
    },
    watch: {
      albumArr() {
        this.genreList();
      },
    },
  };
  </script>
  
  <style lang="scss" scoped>
  @import "../../assets/style/globals.scss";
  
  .search {
    font-size: 2rem;
    margin-bottom: 50px;
  
    select {
      // width: 150px;
      padding: 3px;
      background: $first-color;
      border: none;
      font-size: 1.5rem;
      color: #fff;
      text-transform: uppercase;
    }
  }
  </style>
  