<template>
    <ul>
        <li><a href="">TESTE</a></li>
        <li><a href="">TESTE 1</a></li>
        <li><a href="">TESTE 2</a></li>
    </ul>
</template>

<script>
export default{
    name: 'Header'
}
</script>

<style scoped>
ul {
    list-style: none;
    display: flex;
    background-color: darkslategray;
}

li{
    margin-right: 10px;
}
a{
    color: azure;
    text-decoration: none;
    transition: .5s;
}
a:hover{
    color: cornflowerblue;
}

</style>