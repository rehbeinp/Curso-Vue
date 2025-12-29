<template>
    <form action="" @submit="enviarFormulario($event)">
        <div> <input type="text" v-model="nome"></div>
        <div> <input type="text" v-model="email"></div>
        <div>
            <submit />
        </div>
    </form>
</template>

<script>
import InputTextVue from "./form/InputText.vue";
import Submit from "./form/Submit.vue";

export default {
    name: 'Form',
    components: {
        InputTextVue,
        Submit
    },
    data(){
        return{
            nome:'',
            email:''
        }
    },
    methods: {
        enviarFormulario(e) {
            const nome = this.nome;
            const email = this.email;

            e.preventDefault();
            console.log(nome," - ", email)
        }
    }
}
</script>