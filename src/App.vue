<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <h1>Counter: {{ counter$ }}</h1>
    <h1>Counter + 1: {{ counterPlus1 }}</h1>
  </div>
</template>

<script>
import { counter$ } from './observables'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  subscriptions() {
    return { counter$ }
  },
  computed: {
    counterPlus1() {
      return this.counter$ + 1
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
