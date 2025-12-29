<template>
  <div>
    <NavBar :logo="logoSrc" :alt="appName" />
    <router-view />
    <Footer />
  </div>
</template>


<script>
import { RouterLink, RouterView } from 'vue-router';
import NavBar from './components/NavBar.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    RouterView,
    NavBar,
    Footer
  },
  data() {
    return {
      logoSrc: "/img/logo.png",
      appName: "Your Burguer"
    }
  }
}
</script>


<style>
* {
  font-family: Helvetica;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.main-container{
  margin: 50px;
  min-height: 250px;
}

h1{
  text-align: center;
  font-size: 48px;
  margin-bottom: 60px;
  color: black;

}
</style>
