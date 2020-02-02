<template>
  <div id="app">
    <Benchmark
      msg="Welcome to Your Vue.js App"
    />
  </div>
</template>

<script>
import Benchmark from './components/Benchmark.vue'

export default {
  name: 'app',
  components: {
    Benchmark
  }
}
</script>

<style>
#app {
  font-family: 'Times'
}
</style>
