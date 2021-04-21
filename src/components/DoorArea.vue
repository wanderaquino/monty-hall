<template>
    <div class="door-area">
        <Door number ="1" :gifted = "true"/>
        <Door number ="2" :gifted = "false"/>
        <Door number ="3" :gifted = "false"/>
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
        flex-wrap: wrap;
    }
</style>