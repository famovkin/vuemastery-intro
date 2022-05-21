<template>
  <header class="header app__header">
    <h1 class="header__title">{{ title }}</h1>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    title: {
      type: String,
      required: true,
    },
  },
});
</script>

<style lang="scss">
.header {
  background: linear-gradient(-90deg, #84cf6a, #16c0b0);
  -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.57);
  height: 60px;
  display: flex;

  &__title {
    margin: auto;
    color: $white;
    font-size: 34px;
  }
}

.app__header {
  margin-bottom: 40px;
}
</style>
