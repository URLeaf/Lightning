<template>
  <Help />
  <div class="container">
    <form
      @submit.prevent="sendLink"
      enctype="multipart/form-data"
      class="inputs"
    >
      <input class="add" type="text" v-model="linkContent" />
      <button>Short!</button>
    </form>
  </div>
  <div class="responses">
    <div v-for="link in linksRes" :key="link">
      <div class="response linkname">{{ link.link }}</div>
      <span :to="'/' + link.id" class="response">
        {{ window + '/' + link.id }}
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Help from './Help.vue'
import axios from 'axios'

export default defineComponent({
  components: {
    Help,
  },
  data() {
    return {
      linkContent: '',
      linksRes: [] as {
        link: string
        id: string
      }[],
      window: '',
    }
  },
  methods: {
    async sendLink() {
      const link = this.linkContent
      await axios
        .post('/api', {
          link: link,
          id: '',
        })
        .then((res) => {
          console.log(res)
          this.linksRes.push({
            link: res.data.link,
            id: res.data.id,
          })
        })
      this.linkContent = ''
    },
  },
  mounted() {
    this.window = window.location.host
  },
})
</script>

<style scoped>
.container,
.responses {
  width: 900px;
  max-width: 95vw;
  background: #00647d;
  margin: 10px auto;
  border-radius: 10px;
  padding: 10px;
}

.responses {
  background: rgb(186, 194, 196);
  padding: 5px;
}

.response {
  background: #fff;
  padding: 7px;
  margin: 3px 5px;
  border-radius: 5px;
}

.responses > div {
  display: flex;
  justify-content: space-between;
}

.responses span {
  text-decoration: none;
  color: #e3e3e3;
  background: #364448;
  width: 210px;
  text-align: center;
}

.linkname {
  flex-grow: 1;
}

.inputs {
  display: flex;
  justify-content: space-between;
}

.add,
button {
  background: #fff;
  border-radius: 5px;
  padding: 5px;
  font-size: 18px;
  outline: none;
  border: none;
  margin: 0 10px;
}

.add {
  flex-grow: 1;
}

button {
  padding: 0 10px;
}
</style>
