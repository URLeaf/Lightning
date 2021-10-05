<template>
  <div class="logo">
    Lightning
    <img src="../assets/lightning.svg" />
  </div>
  <!-- <div class="desc">Ultra-fast link shorter</div> -->
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({})
</script>

<style scoped>
.logo {
  font-size: calc(45px + 2vw);
  font-weight: 600;
  font-style: italic;
  color: #00647d;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 30px;
}

.logo img {
  display: inline-block;
  width: calc(45px + 2vw);
}

.desc {
  text-align: center;
  font-size: 25px;
}
</style>
