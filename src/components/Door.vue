<template>

    <div class="door-frame" :class="{ 'selected-frame': selected && !open}" >
        <div class="door" @click="e => setSelected(e)" :gifted="gifted" :class="{'door-open': open}">
            <div class="door-number" :class="{'selected-number': selected}" >{{number}}</div>
            <div class="door-handle" @click="e => doorHandleOpen(e)" :class="{'selected-handle': selected}"></div>
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
        --selected-border: solid 5px greenyellow;
        --handle-door-bg: brown;
    }

    .door-frame{
        display: flex;
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
        align-items: flex-end;
        justify-content: center;
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

    .selected-frame {
        border-left: var(--selected-border);
        border-right: var(--selected-border);
        border-top: var(--selected-border);
    }

    .selected-handle {
        background-color: var(--color-selected);
    }

    .selected-number {
        color: var(--color-selected);
    }

    .door-open {
        background: #0009;
    }

    .door-open .door-handle,
    .door-open .door-number {
        display: none;
    }

</style>