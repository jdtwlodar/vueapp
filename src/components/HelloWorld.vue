<template>
        <div>
        <b-navbar toggleable="lg" type="dark" variant="info">
          <b-navbar-brand href="#">
            <img class="app__logo" src="../assets/images/logo.png" alt />
          </b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
              <b-nav-item href="#">Link</b-nav-item>
              <b-nav-item href="#">Link</b-nav-item>
              <b-nav-item href="#">Link</b-nav-item>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
      </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      title: 'Jestem menu'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
