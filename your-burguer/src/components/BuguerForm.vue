<template>
    <div>
        <Message :msg="msg" v-show="msg"/>
        <div class="burguer-form">
            <form @submit="creatBurguer">
                <div class="input-container">
                    <label for="customer name">Customer Name:</label>
                    <input type="text" id="customer-name" name="costumerName" v-model="customerName"
                        placeholder="Customer Name">
                </div>
                <div class="input-container">
                    <label for="bread">Type of Bread:</label>
                    <select name="bread" id="type-bread" v-model="bread">
                        <option value="">Select your bread</option>
                        <option v-for="bread of breadForm" :key="bread.id" :value="bread.tipo">
                            {{ bread.tipo }}</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="meat">Type of Meat:</label>
                    <select name="meat" id="type-meat" v-model="meat">
                        <option value="">Select your bread</option>
                        <option v-for="meat of meatForm" :key="meat.id" :value="meat.tipo">{{ meat.tipo }}</option>
                    </select>
                </div>
                <div class="input-container" id="side-dishes-container">
                    <label for="sideDishes" id="side-dishes-label">Choose the side dishes:</label>
                    <div v-for="sideDishe of sideDishesForm" :key="sideDishe.id" class="checkbox-container">
                        <span>{{ sideDishe.tipo }}</span>
                        <input type="checkbox" name="sideDishes" v-model="sideDishes" :value="sideDishe.tipo">
                    </div>
                </div>
                <div class="input-container">
                    <input type="submit" id="submit-burguer" name="submitBurguer" value="Make The Burguer">
                </div>
            </form>
        </div>

    </div>
</template>

<script>
import Message from './Message.vue';
export default {
    name: "BurguerForm",
    data() {
        return {
        meatForm: null,
        breadForm: null,
        sideDishesForm: null,
        customerName: null,
        meat: null,
        bread: null,
        sideDishes: [],
        status: "Solicitado",
        msg: null
        }
    },
    methods: {
        async getIngredients() {
            const req = await fetch("http://localhost:3000/ingredientes");
            const data = await req.json();
            

            this.meatForm = data.carnes;
            this.breadForm = data.paes;
            this.sideDishesForm = data.opcionais;

        },
        async creatBurguer(e) {
            e.preventDefault();
            const pedido = {
                "name": this.customerName,
                "meat": this.meat,
                "bread": this.bread,
                "sideDishes": Array.from(this.sideDishes),
                "status": this.status
            }

            const pedidoJson = JSON.stringify(pedido)
            const req = await fetch("http://localhost:3000/burgers",{
                method: "POST",
                headers: {"Content-Type": "application/json"},
                body: pedidoJson
            });
            const res = await req.json()

            this.msg = `Pedido ${res.id} realizado com sucesso!!`
            setTimeout(()=>{this.msg=""},3000)

            this.customerName = "";
            this.meat = "";
            this.bread = "";
            this.sideDishes = [];
        }
    },
    mounted() {
        this.getIngredients();
    },
    components:{
        Message
    }
}
</script>



<style scoped>
.burguer-form {
    display: flex;
    align-items: center;
    justify-content: center;
    max-width: 400px;
    margin: 0 auto;
}

.input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}

label {
    font-weight: bold;
    display: flex;
    margin: 15px;
    padding: 5px 10px;
    border-left: 4px solid gold;
    align-items: center;
}

input,
select {
    padding: 5px 10px;
    width: 300px;
}

#side-dishes-container {
    flex-direction: row;
    flex-wrap: wrap;
}

#side-dishes-label {
    width: 100%;
}

.checkbox-container {
    display: flex;
    align-items: flex-end;
    width: 50%;
    margin: 20px;
}

.checkbox-container span,
.checkbox-container input {
    width: auto;
}

.checkbox-container span {
    margin-right: 10px;
}

#submit-burguer {
    background-color: darkred;
    color: gold;
    font-weight: bold;
    border: 3px solid #222;
    font-size: 16px;
    margin: -10 auto;
    cursor: pointer;
    transition: 0.3s;
}

#submit-burguer:hover {
    color: darkred;
    background-color: gold;
    border: 3px solid rgb(175, 150, 12);
}
</style>