<template>
    <div id="app">
        <h1>Monty Hall Problem</h1>
        <DoorArea/>
    </div>
</template>

<script>
import DoorArea from "./components/DoorArea";

export default {
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

    .door-area {
        display: flex;
        flex-wrap: wrap;
        height: auto;
        align-items: center;
        justify-content: center;
    }

</style>