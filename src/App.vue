<template>
    <div id="app">
        <h1>Monty Hall Problem</h1>
        <DoorArea :doorsAmount="doorsAmount" :giftedDoor="giftedDoor"/>
    </div>
</template>

<script>
import DoorArea from "./components/DoorArea";

export default {
    name: "App",
    data: function () {
        return {
            started: false,
            doorsAmount: 10,
            giftedDoor: 7
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
</style>