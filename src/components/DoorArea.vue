<template>
    <div class="door-area">
        <Door/>
        <Door/>
        <Door/>
    </div>
</template>

<script>
import Door from "./Door"

export default {
    components: {Door}
}
</script>

<style>
    .door-area {
        display: flex;
        height: 40%;
        align-items: center;
        justify-content: center;
    }
</style>