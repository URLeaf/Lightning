<template>
  <Header />
  <Input />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Header from '../components/Header.vue'
import Input from '../components/Input.vue'

export default defineComponent({
  name: 'Home',
  components: {
    Header,
    Input,
  },
})
</script>
