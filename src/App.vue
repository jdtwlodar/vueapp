<template>
  <div id="app">
    <div class="container-fluid px-0">
        <div class="d-flex flex-column flex-md-row">
      <div class="order-2 order-md-1 col-md-6 px-0">
        <Content />
      </div>
      <div class="order-2 order-md-1 col-md-6 px-0"></div>
    </div>
    </div>
  </div>
</template>

<script>
import Content from "./components/Content.vue";


export default {
  name: "App",
  components: {
    Content,

  },
};
</script>

<style lang="scss">
@import "node_modules/bootstrap/scss/bootstrap";
.app {
  &__logo {
    width: 2rem;
  }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
