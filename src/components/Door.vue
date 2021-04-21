<template>

    <div class="door-frame">
        <div class="door" @click="e => doorHandleOpen(e)" :gifted="false" :class="{opened: open}">
            <div class="door-number">{{number}}</div>
            <div class="door-handle"></div>
        </div>
        <Gift v-if="gifted === true && open === true"/>
    </div>

</template>

<script>
import Gift from "./Gift";

export default {
    data: function () {
            return {
                selected: false,
                open: false
            }
        },
    props: {
        number: {},
        gifted: {type: Boolean},
    },
    methods: {
        setSelected () {
            this.selected = !this.selected;
        },
        setOpened () {
            this.open = !this.open;
        },
        doorHandleOpen(e) {
            if (e.target.classList.contains('door-handle')) {
                this.setOpened();
                console.log("Porta aberta...");
            } else {
                this.setSelected();
            }
        }
    },
    computed: {},
    components: {Gift}
}
</script>

<style>

    :root {
        --frame-door: 5px solid sienna;
        --color-selected: greenyellow;
        --handle-door-bg: brown;
    }

    .door-frame{
        position: relative;
        height: 220px;
        width: 140px;
        
        border-left: var(--frame-door);
        border-right: var(--frame-door);
        border-top: var(--frame-door);
        border-bottom: 10px solid gray;
        margin-bottom: 20px;
        margin-left: 12px;

        box-sizing: border-box;
    }

    .door {
        display: flex;
        position: absolute;
        justify-content: center;
        top: 0;
        width: 100%;
        height: 100%;
        background-color: chocolate;
    }
    .door-number {
        position: absolute;
        font-size: 2rem;
        color: whitesmoke;
        font-weight: 700;
    }

    .door-handle {
        position: absolute;
        height: 25px;
        width: 25px;
        margin-left: 10px;
        border-radius: 15px;
        background-color: var(--handle-door-bg);
        align-self: center;
        left: 0;
    }

    .selected {
        background-color: var(--color-selected);
    }

    .opened {
        background: linear-gradient(22deg, rgba(97,92,92,1) 22%, rgba(23,25,25,1) 56%);
    }

</style>