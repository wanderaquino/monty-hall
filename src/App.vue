<template>
    <div id="app">
        <h1>Monty Hall Problem</h1>
        <div class="form" v-if="!started">
            <label for="form-doors-amount">Quantas portas? </label>
            <input type="text" id="form-doors-amount" value=3 size="4" v-model.number="doorsAmount">
            <label for="form-doors-gifted">Qual porta premiada? </label>
            <input type="text" id="form-doors-gifted" value=2 size="4" v-model.number="giftedDoor">
            <span class="pre-game-error" v-if="errorMessage || false">{{errorMessage}}</span>
            <button class="form-doors-button-start" @click="startGame()">Iniciar</button>
        </div>
        <div v-if="started">
            <DoorArea :doorsAmount="doorsAmount" :giftedDoor="giftedDoor"/>
        </div>
        <button class="button-restart" v-if="started" @click="reloadGame()">Reiniciar</button> 
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
            giftedDoor: null,
            errorMessage: null
        }
    },
    methods: {
        checkPreGame() {
            const checkData = new RegExp(/^\d+$/);
            if(!(checkData.test(this.doorsAmount) && checkData.test(this.giftedDoor))) {
                return {code: 0, 
                errorMessage: "Quantidade de portas precisa ser maior que 01 e uma porta precisa ser premiada"}
            }
            return {code: 1, description: "Sucesso"};
        },
        startGame() {
            const checkGame = this.checkPreGame();

            if (checkGame.code != 0) {
                this.started = true;
            }
            this.errorMessage = checkGame.errorMessage;
        },
        reloadGame() {
            this.started = false;
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
    .pre-game-error {
        color: red;
        font-size: 1.2rem;
        margin-bottom: 15px;
    }
    .button-restart {
        width: 90px;
        align-self: center;
    }

</style>