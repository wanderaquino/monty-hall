<template>

    <div class="door" @click="e => doorHandleOpen(e)">
        <div class="door-frame-up" :class="{selected: selected}"></div>
        <div class="door-frame-right" :class="{selected: selected}"></div>
        <div class="door-frame-left" :class="{selected: selected}"></div>
        <div class="door-frame-floor"></div>
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
        --frame-door-color: sienna;
        --floor-door: 10px solid gray;
        --color-selected: greenyellow;
    }

    .door {
        position: relative;
        display: flex;
        width: 140px;
        height: 220px;
        background-color: peru;
        justify-content: space-between;
        margin: 7px 7px 7px 0;
        box-sizing: border-box;
    }

    .door-frame-up,
    .door-frame-floor{
        position: absolute;
        height: 5px;
        width: 100%;
        background: var(--frame-door-color);
    }

    .door-frame-up{
        align-self: flex-start;
    }

    .door-frame-floor {
        background: gray !important;
        height: 7px !important;
        align-self: flex-end;
    }


    .door-frame-left,
    .door-frame-right {
        height: 100%;
        width: 5px;
        background: var(--frame-door-color);
        align-self: center;
    }

    .door-frame-left {
        justify-self:left;
    }

    .door-frame-right {
        justify-self:right;
    }

    .selected {
        background-color: var(--color-selected);
    }

    .opened {
        opacity: 40%;
    }

</style>