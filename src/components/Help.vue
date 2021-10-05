<template>
  <div class="help">
    Type text here
    <img src="../assets/arrow.svg" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({})
</script>

<style scoped>
.help {
  font-size: 25px;
  font-weight: bold;
  text-align: center;
  margin: 10px;
  padding-bottom: 40px;
}

img {
  position: absolute;
  width: 50px;
  transform: rotate(90deg) translateX(10px) translateY(-10px);
}
</style>
