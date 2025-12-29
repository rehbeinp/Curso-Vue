<template>
    <div>
        <button @click="primeiraAcao($event), segundaAcao($event), terceiraAcao($event)">Acionar multiplos eventos</button>
        <p>{{ dadoExibido }}</p>
    </div>
</template>


<script>

export default {
    name: 'MultiplosEventos',
    data() {
        return {
            dadoExibido: ''
        }
    },
    methods: {
        primeiraAcao(e) {
            this.dadoExibido = "Primeiro evento ativado"
        },
        segundaAcao(e){
            setTimeout(()=>this.dadoExibido = "Segundo evento ativado ;)", 500)
        },
        terceiraAcao(e){
            setTimeout(()=>this.dadoExibido = "", 1500)
        }
    }
}
</script>

<style scoped>
div {
    margin: 100px;
}
</style>