<template>
  <button
    class="button"
    :class="{ 'button_disabled': !enabled }"
  >
    <slot></slot>
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    enabled: {
      type: Boolean,
      default: true,
    },
  },
});
</script>

<style lang="scss">
  .button {
    color: $white;
    background: $dark-blue;
    height: 60px;
    max-width: 200px;
    padding: 0 20px;
    border-radius: 5px;
    font-size: 18px;
    box-shadow: inset 0 -0.6em 1em -0.35em rgba(0, 0, 0, 0.17),
    inset 0 0.6em 2em -0.3em rgba(255, 255, 255, 0.15),
    inset 0 0 0em 0.05em rgba(255, 255, 255, 0.12);
    cursor: pointer;
  }

  .button_disabled {
    background: $gray;
    cursor: not-allowed;
  }
</style>
