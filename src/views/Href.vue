<template>
  <div></div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import axios from 'axios'

export default defineComponent({
  created() {
    axios.get('/get/' + window.location.pathname).then((res) => {
      window.location.href = '//' + res.data
    })
  },
})
</script>
