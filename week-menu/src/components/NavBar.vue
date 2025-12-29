<template>
    <div id="navbar-container">
        <RouterLink to="/">Receitas</RouterLink>
        <RouterLink to="/receitaSemana">Receitas da Semana</RouterLink>
        <RouterLink to="/" id="logosrc">
            <img :src="logo" :alt="descricao" id="logo">
        </RouterLink>
    </div>
</template>


<script>

export default {
    name: "NavBar",
    props: ["logo", "descricao"]
}
</script>


<style scope>
#navbar-container {
    font-size: 18px;
    background-color: rgb(140, 82, 40);
    padding: 15px 40px;
    margin: 0;
    display: flex;
    align-items: center;
    justify-content: flex-start;
}

#navbar-container #logosrc {
    margin-right: 0;
    margin: auto;
}

#logo {
    width: 60px;
    height: 50px;
}

#navbar-container a {
    text-decoration: none;
    margin: 15px;
    color: aliceblue;
    align-items: start;
    transition: 0.3s;
}

#navbar-container a:hover{
    color: rgb(232, 154, 99);
}
</style>