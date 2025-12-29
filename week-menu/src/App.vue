<template>
  <div>
    <NavBar :logo="imgLogo" :descricao="appName"/>
  </div>
</template>


<script>
import { RouterLink, RouterView } from 'vue-router';
import NavBar from './components/NavBar.vue';

export default {
  name: 'App',
  components: {
    RouterView,
    NavBar
  },
  data() {
    return {
      imgLogo: "/img/image.png",
      appName:"WeekMenu"
    }
  }
}
</script>


<style>
*{
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  padding: 0;
  margin:0;
  box-sizing: border-box;
}

.main-container{
  margin: 50px;
  min-height: 250px;
}
</style>
