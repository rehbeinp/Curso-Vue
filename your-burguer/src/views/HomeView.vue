<template>
  <div>
    <Banner/>
    <div class="main-container">
      <h1>Monte seu lanche</h1>
      <BuguerFormVue/>
    </div>
  </div>
</template>


<script>
import Banner from '@/components/Banner.vue';
import BuguerFormVue from '../components/BuguerForm.vue';
export default{
  name:"Home",
  components:{
    Banner,
    BuguerFormVue
  }
}
</script>