<template>
  <Background />
  <router-view />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Background from './components/Background.vue'
export default defineComponent({
  components: {
    Background,
  },
})
</script>

<style lang="scss">
@import './styles/main.scss';
* {
  font-family: 'Rubik';
  box-sizing: border-box;
}

body {
  background: #161616;
  color: #e3e3e3;
}
</style>
