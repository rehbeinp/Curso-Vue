<template>
   <div>  
    <h1> Olá, Mundo!! </h1>
    <p>Meu nome é {{ firtName }} {{ lastName }}.</p>
    <MultiplosEventos/>
    <Reutilizacao/>
    <Reutilizacao/>
    <Reutilizacao/>
    <Reutilizacao/>
    <Reutilizacao/>
   </div>
</template>

<script>
import MultiplosEventos from './MultiplosEventos.vue';
import Reutilizacao from './Reutilizacao.vue';
export default{
        data(){
            return{
                firtName: 'Paula',
                lastName: 'Rehbein'
            }
        },
        components:{
            MultiplosEventos,
            Reutilizacao
        }

    }
</script>