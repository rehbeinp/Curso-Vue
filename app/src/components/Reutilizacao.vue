<template>
    <div>
        <button @click="ativar($event)">Ativar texto</button>
        <p v-show="ativo">Texto ativado</p>
    </div>
</template>

<script>
export default{
    name:'Reutilizacao',
    data(){
        return {
            ativo: false
        }
    },
    methods:{
        ativar(e){
            this.ativo = !this.ativo
        }
    }
}
</script>