<template>
    <div>
        <Picture/>
        <p>{{ email }}</p>
        <p v-if="estouTrabalhando">Estou trabalhando</p>
        <p v-else>Não estou trabalhando no momento </p>
        <h3>Conheço as seguintes tecnologias: </h3>
        <ul>          
            <li v-for="(conhecimento, index) in conhecimentosTecnologicos" v-bind:key="index">{{conhecimento}}</li>
        </ul>

        <h3>Tecnologias de Front-End:</h3>
        <ul>
            <li v-for="conhecimento in conhecimentoFrontEnd" v-bind:key="conhecimento.id">
                {{ conhecimento.tecnologia }}
            </li>
        </ul>
        <button @click="showEmail">{{textoBotaoEmail}}</button>
        <p v-show="receberEmail">Mande um email para mim: {{ email }}</p>
        <p>Para ver meu git <a v-bind:href="meuLink" target="_blank">clique aqui</a> </p>
    </div>
</template>

<script>
  import Picture from './Picture.vue';

export default{
    name: 'Info',
    components: {
        Picture
    },
    props:{
        email: String
    },
    data(){
        return{
            estouTrabalhando: false,
            receberEmail: false,
            meuLink: 'https://google.com',
            textoBotaoEmail: 'Mandar Email',
            conhecimentosTecnologicos: [] = ['C++', 'Python', 'Spark', 'Vue', 'TypeScript'],
            conhecimentoFrontEnd: [
                {id: 1, tecnologia: 'TypeScript'},
                {id: 2, tecnologia: 'Vue'},
                {id: 3, tecnologia: 'Angular'}
            ]
        }
    },
    methods:{
        showEmail(){
            this.receberEmail = !this.receberEmail
            if(!this.receberEmail){
                this.textoBotaoEmail= 'Mandar Email'
            }else {this.textoBotaoEmail = 'Esconder email'}
        }
    }

}
</script>