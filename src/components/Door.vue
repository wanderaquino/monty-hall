<template>
    <div class="door">
        <DoorHandle/>
    </div>

</template>

<script>
import DoorHandle from "./DoorHandle"

export default {
    components: {DoorHandle},
    props: {
        selected: {type: Boolean}
    }
}
</script>

<style>

    :root {
        --frame-door-border: 5px solid sienna;
        --floor-door: 10px solid gray;
        --color-selected: greenyellow;
    }

    .door {
        display: flex;
        align-items: center;
        width: 140px;
        height: 220px;
        background-color: peru;
        border-top: var(--frame-door-border);
        border-left: var(--frame-door-border);
        border-right: var(--frame-door-border);
        border-bottom: var(--floor-door);
        margin: 7px 7px 7px 0;
        box-sizing: border-box;
    }

    .selected {
        border-color: var(--color-selected);
    }
</style>