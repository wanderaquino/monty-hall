<template>

    <div class="door" @click="e => doorHandleOpen(e)" :class="{selected: selected}">
        <DoorHandle :selected="selected" />
    </div>

</template>

<script>
import DoorHandle from "./DoorHandle"

export default {
    data: function () {
            return {
                selected: false,
                gifted: false,
                open: false
            }
        },
    methods: {
        setSelected () {
            this.selected = !this.selected;
        },
        doorHandleOpen(e) {
            if (e.target.classList.contains('door-handle')) {
                this.open = true;
                console.log("Porta aberta...");
            } else {
                this.setSelected();
            }
        }
    },
    computed: {},
    components: {DoorHandle}
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