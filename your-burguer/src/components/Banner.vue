<template>
    <div id="main-banner">
        <h1>Make Your Burguer</h1>
    </div>
</template>


<script>
export default{
    name:"Banner"
}
</script>


<style>
    #main-banner{
        background-image: url('/img/hamburguer.jpg');
        background-position: 0 -250px;
        background-size: cover;
        height: 500px;
        display: flex;
        align-items: center;
        justify-content: flex-start;
        border-bottom: 4px solid gold;
    }
    #main-banner h1{
        color: #fff;
        text-align: center;
        font-size: 50px;
        background-color: darkred;
        padding: 20px 40px;
        border-right: 6px solid gold;
    }
</style>