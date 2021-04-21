<template>
    <div class="door-area">
        <div v-for="i in doorsAmount" :key=i>
            <Door :number =i :gifted = "i === giftedDoor"/>
        </div>
    </div>
</template>

<script>
import Door from "./Door"

export default {
    name: "DoorArea",
    props: {
        doorsAmount: {type: Number},
        giftedDoor: {type: Number},
        gifted: {type: Boolean}
    },
    components: {Door}
}
</script>

<style>
    .door-area {
        display: flex;
        height: auto;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
    }
</style>