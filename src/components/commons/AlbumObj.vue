<template>
    <div class="album">
      <img :src="album.poster" :alt="album.title" />
      <h3>{{ album.title }}</h3>
      <h4>
        {{ album.author }} <br />
        {{ album.year }}
      </h4>
    </div>
  </template>
  
  <script>
  export default {
    name: "AlbumObj",
    props: {
      album: Object,
    },
  };
  </script>
  
  <style lang="scss" scoped>
  @import "../../assets/style/globals.scss";
  
  .album {
    padding: 20px;
    width: 220px;
    background: $first-color;
    text-align: center;
  
    img {
      height: 170px;
      width: 100%;
      margin-bottom: 30px;
    }
  
    h3 {
      width: 100%;
      font-size: 1.6rem;
      text-transform: uppercase;
      margin-bottom: 30px;
    }
  
    h4 {
      width: 100%;
      font-size: 1.3rem;
      color: #5e7780;
    }
  }
  </style>
  