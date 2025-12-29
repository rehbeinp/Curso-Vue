<template>
    <div class="container-message">
        <p> {{ msg }}</p>
    </div>
</template>

<script>
export default {
    name: "Message",
    props: {
        msg: String
    }

}
</script>


<style scoped>
.container-message {
    color: rgb(3, 60, 3);
    background-color: rgb(197, 233, 197);
    margin: 15px auto;
    padding: 15px;
    border: 2px solid rgb(143, 195, 143);
    border-radius: 5px;
    box-sizing: 400px;
    max-width: 400px;
}
</style>