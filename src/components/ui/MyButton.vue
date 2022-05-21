<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script lang="ts">
</script>

<style lang="scss">
  .button {
    color: $white;
    background: $dark-blue;
    height: 60px;
    padding: 0 20px;
    border-radius: 5px;
    font-size: 18px;
    box-shadow: inset 0 -0.6em 1em -0.35em rgba(0, 0, 0, 0.17),
    inset 0 0.6em 2em -0.3em rgba(255, 255, 255, 0.15),
    inset 0 0 0em 0.05em rgba(255, 255, 255, 0.12);
    cursor: pointer;
  }
</style>
