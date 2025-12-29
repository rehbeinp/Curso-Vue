<template>
    <div>
      <h2>Essas são as informações de: {{ firstName }} </h2>
      <Info :email="email" />
      <Form/>

    </div>
</template>

<script>

  import Info from './Info.vue';
  import Form from './Form.vue';

  export default{
    name: 'Pessoa',
    components: {
      Info,
      Form
    },
    data(){
      return {
        firstName: 'Paula',
        email: 'paula@gmail.com'
      }

    }
  }
</script>