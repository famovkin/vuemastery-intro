<template>
  <my-header title="Vue mastery"></my-header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MyHeader from '@/components/MyHeader.vue';

export default defineComponent({
  name: 'App',
  components: {
    MyHeader,
  },
});
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  min-width: 320px;
}
</style>
