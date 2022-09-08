<template>
    <div class="container">
      <SearchObj @search="getFilterAlbum" :albumArr="albumArr" />
      <div v-if="!loading">
        <AlbumObj
          v-for="(album, index) in callFilterArr"
          :key="index"
          :album="album"
        />
      </div>
      <LoaderObj v-else />
    </div>
  </template>
  
  <script>
  import axios from "axios";
  import AlbumObj from "../commons/AlbumObj.vue";
  import LoaderObj from "../commons/LoaderObj.vue";
import SearchObj from "../commons/SearchObj.vue";
  
  
  export default {
    name: "ListaAlbum.vue",
    data() {
      return {
        apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
        albumArr: [],
        loading: true,
        filterGenre: "",
      };
    },
    components: {
    AlbumObj,
    LoaderObj,
    SearchObj
},
    created() {
      this.getAlbum();
    },
    methods: {
      getAlbum() {
        axios
          .get(this.apiURL)
          .then((risposta) => {
            this.albumArr = risposta.data.response;
            console.log(risposta.data.response);
            console.log(this.albumArr);
            this.loading = false;
            this.filterArr = this.albumArr;
          })
          .catch(function (error) {
            console.log(error);
          });
      },
      getFilterAlbum(selected) {
        this.filterGenre = selected;
      },
    },
    computed: {
      callFilterArr() {
        return this.albumArr.filter((album) => {
          return album.genre.includes(this.filterGenre);
        });
      },
    },
  };
  </script>
  
  <style lang="scss" scoped>
  @import "../../assets/style/globals.scss";
  
  .container {
    margin: auto;
    padding: 50px;
    width: 70%;
  
    & > div {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
    }
  }
  </style>
  