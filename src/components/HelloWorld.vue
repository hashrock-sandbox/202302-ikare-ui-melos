<script>
import { merosu } from "../../merosu"

const items = merosu.split("/")

export default {
  data() {
    return {
      msg: [],
      items
    }
  },
  methods: {
    input(str) {
      this.msg.push(str)
    },
    clear() {
      this.msg.splice(0, this.msg.length)
    },
    remove(index) {
      this.msg.splice(index, 1)
    }
  }
}
</script>

<template>
  <div>
    セミナーの感想をお寄せください。
  </div>
  <div style="margin-top:4rem;">
    名前：
    <input type="text" value="メロス">
  </div>
  <div>
    職業：
    <input type="text" value="牧人">
  </div>
  <p>
    感想をお寄せください

  </p>
  <div class="input">
    <div class="area__badge" v-for="(m, idx) in msg">
      {{ m }}
      <button @click="remove(idx)" class="area__badge__delete">x</button>
    </div>
  </div>
  <button @click="clear">クリア</button>
  <details>
    <summary>
      ここから選択してください
    </summary>
    <button v-for="item in items" @click="input(item)">{{ item }}</button>
</details>
  <div>
    <button>送信</button>
  </div>
</template>

<style>
.input {
  border: 1px solid black;
  min-height: 5rem;
}

input {
  font-size: inherit;
}

details {
  height: 10rem;
  overflow-y: auto;
}


body {
  font-size: 150%;
  max-width: 960px;
  margin: 0 auto;
}

.area {
  font-size: 2rem;
  border: 1px solid black;
  min-height: 5rem;
  max-height: 10rem;
  overflow-y: auto;
}

.area__badge {
  font-size: 1rem;
  display: inline-block;
  border-radius: 0.5rem;
  padding: 0.1em;
  position: relative;
}

.area__badge:hover>.area__badge__delete {
  display: inline-block;
}

.area__badge:hover {
  background-color: aquamarine;
}

.area__badge__delete {
  display: none;
  font-size: 0.5rem;
  position: absolute;
  top: 0;
  right: -1rem;
  z-index: 1;
}

.read-the-docs {
  color: #888;
}</style>
