<template>
    <header>
      <img src="../../assets/img/logo.png" alt="Spotify" />
    </header>
  </template>
  
  <script>
  export default {
    name: "HeaderMain",
  };
  </script>
  
  <style lang="scss" scoped>
  @import "../../assets/style/globals.scss";
  
  header {
    background: $first-color;
  
    img {
      margin: 10px;
      height: 70px;
    }
  }
  </style>