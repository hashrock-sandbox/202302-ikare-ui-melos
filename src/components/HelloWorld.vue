<script>
import { merosu } from "../../merosu"

const items = merosu.split("/")

export default {
  data() {
    return {
      msg: "",
      items
    }
  },
  methods: {
    input(str) {
      this.msg += str
    },
    clear() {
      this.msg = ""
    }
  }
}
</script>

<template>
  <div>

  </div>
  <div style="">
    {{ msg }}
  </div>
  <button @click="clear">クリア</button>
  <details>
    <summary>
      ここから選択してください
    </summary>
    <button v-for="item in items" @click="input(item)">{{ item }}</button>
  </details>
</template>

<style scoped>
.area {
  font-size: 2rem;
  border: 1px solid black;
  min-height: 5rem;
}

.read-the-docs {
  color: #888;
}
</style>
