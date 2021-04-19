<template>
  <div class="door-handle" :class="{selected: selected}"></div>
</template>

<script>
export default {
    props: {
    selected: {type: Boolean}
    }
}
</script>

<style>
    :root {
        --handle-door-bg: sienna;
    }
    .door-handle {
        position:absolute;
        height: 25px;
        width: 25px;
        margin-left: 10px;
        border-radius: 15px;
        background-color: var(--handle-door-bg);
        align-self: center;
    }

    .selected {
        background-color: var(--color-selected);
    }
</style>