<template>
   <div>
    <img :src="foto" :alt="descricao">
    <MudarImagemVue @mudarImagem = "alterarImagem()" />
    </div> 
</template>

<script>
import MudarImagemVue from './MudarImagem.vue'

export default{
    name:'Picture',
    components:{
        MudarImagemVue
    },
    data(){
        return{
            foto: '/img/imagecopy.png',
            descricao: 'Gato Preto'
        }
    },
    methods:{
        alterarImagem(){
            if(this.foto=='/img/image.png'){
                this.foto= '/img/imagecopy.png'
            }else {
                this.foto='/img/image.png'
            }
            
        }
    }
}
</script>