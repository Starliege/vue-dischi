<template>
  <div id="app">
    <HeaderMain />
    <PageMain />
  </div>
</template>

<script>
import HeaderMain from "./components/macro/HeaderMain.vue";
import PageMain from "./components/macro/PageMain.vue";


export default {
  name: "App",
  components: {
    HeaderMain,
    PageMain
},
};
</script>

<style lang="scss">
@import "./assets/style/globals.scss";

body {
  background: #000;
}
</style>