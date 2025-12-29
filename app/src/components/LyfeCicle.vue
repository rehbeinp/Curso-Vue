<template>
    <h1> Meu nome é: {{ myName }}</h1>
</template>

<script>
  export default {
    name: 'LyfeCicle',
    data(){
        return{
            myName: 'não sei'
        }
    },
    created(){
        setTimeout(()=>{
            this.myName='Paula'
        }, 1000)
        
    },
    mounted(){
        setTimeout(()=>{
            this.myName = 'Lina'
        }, 2000)
    }
  }
</script>