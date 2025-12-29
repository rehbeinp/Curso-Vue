<template>
    <div id="nav">
        <RouterLink to="/" id="logoSrc">
            <img :src="logo" :alt="alt" id="logo">
        </RouterLink>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/pedidos">Orders</RouterLink>
    </div>
</template>

<script>
export default {
    name: 'NavBar',
    props: ["logo", "alt"]
}
</script>

<style scoped>  
    #nav {
        background-color: darkred;
        border-bottom: 4px solid #111;
        padding: 15px 50px;
        display: flex;
        justify-content: flex-end;
        align-items: center;
}

    #nav #logoSrc{
        margin: auto;
        margin-left: 0;

    }
    #logo{
        width: 50px;
        height: 50px;
    }

    #nav a{
        color:gold;
        text-decoration: none;
        margin: 12px;
        transition: 0.3s;
    }
    #nav a:hover{
        color: #fff;
    }
</style>