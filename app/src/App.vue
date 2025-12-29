<template>
    <div> 
        <Header/>
        <PrimeiroComponente/>
        <LyfeCicle/>
        <Pessoa/>
    </div>
</template>
  
<script>
  import Header from './components/Header.vue';
  import PrimeiroComponente from './components/PrimeiroComponente.vue';
  import LyfeCicle from './components/LyfeCicle.vue';
  import Pessoa from './components/Pessoa.vue';
  export default {
    name: "App",
    components: {
        PrimeiroComponente,
        LyfeCicle,
        Pessoa,
        Header
    }
  };
</script>


<style>
body{
  background-color: darkcyan;
  color: honeydew;
}
a{
  color:darkseagreen;
}
</style>