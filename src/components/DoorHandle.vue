<template>
  <div class="door-handle"></div>
</template>

<script>
export default {

}
</script>

<style>
    :root {
        --handle-door-bg: sienna;
    }

    .door-handle {
        height: 25px;
        width: 25px;
        margin-left: 5px;
        border-radius: 15px;
        background-color: var(--handle-door-bg);
    }

    .selected {
        background-color: var(--color-selected);
    }
</style>