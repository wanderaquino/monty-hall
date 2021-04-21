<template>
    <div id="app">
        <h1>Monty Hall Problem</h1>
    <div class="form" v-if="!started">
        <label for="form-doors-amount">Quantas portas? </label>
        <input type="text" id="form-doors-amount" value=3 v-model.number="doorsAmount">
        <label for="form-doors-gifted">Qual porta premiada? </label>
        <input type="text" id="form-doors-gifted" value=2 v-model.number="giftedDoor">
        
        <button class="form-doors-button-start" @click="startGame()">Iniciar
        </button> 
    </div>
        <div v-if="started">
            <DoorArea :doorsAmount="doorsAmount" :giftedDoor="giftedDoor"/>
        </div>
    </div>
</template>

<script>
import DoorArea from "./components/DoorArea";

export default {
    name: "App",
    data: function () {
        return {
            started: false,
            doorsAmount: null,
            giftedDoor: null
        }
    },
    methods: {
        startGame() {
            this.started = true;
        }
    },
    components: {DoorArea}
}
</script>

<style>

    * {
        font-family: Calibri, sans-serif;
    }

    body {
        margin: 0;
    }

    #app{
        display: flex;
        flex-direction: column;
        background: whitesmoke;
        height: 100vh;
    }

    #app > h1 {
        color: gray;
        text-align: center;
    }

    .form {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .form > label {
        font-size: 1.2rem;
    }

    .form input {
        justify-self: left;
    }

    .form, 
    .form > label ~ input {
        margin-bottom: 12px;
    }   
</style>