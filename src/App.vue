<template>
  <div id="app">
    <img src="./logo.svg" />
    <h1>Hello <a href='https://github.com/vuejs/vue' target='__blank'>Vue 2</a> and <a
        href='https://github.com/vueuse/vueuse' target='__blank'>VueUse</a>!</h1>

    <br /><br />

    <h3>
      Ref History {{ counter }}

      <button @click="counter++">
        counter ++
      </button>

      <button @click="counter--">
        counter --
      </button>

      <button @click="undo">
        undo
      </button>

      <button @click="redo">
        redo
      </button>
    </h3>
    <p><a href='https://github.com/BaoBao2022/vue2-history-example' target='__blank'>Source</a></p>
  </div>
</template>

<script>
import { useRefHistory } from '@vueuse/core'
import { ref } from 'vue'

export default {
  setup() {

    const counter = ref(0)
    const { history, undo, redo } = useRefHistory(counter)

    return {
      history,
      counter,
      undo,
      redo
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Noto+Serif&display=swap');

html,
body,
h1,
h2,
h3,
p {
  font-family: 'Noto Serif', serif;
  user-select: none;
}

#app {
  text-align: center;
  color: rgba(0, 0, 0, 0.4);
}

img {
  width: 500px;
}

a {
  color: #41b883;
  text-decoration: none;
  cursor: pointer;
}
</style>
