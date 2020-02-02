<template>
  <div class="benchmark">
    <button
      v-on:click="add1000Elements"
    >
      Add 10,000 div elements
    </button>
    <button
      v-on:click="remove1000Elements"
    >
      Remove 10,000 div elements
    </button>
    <BenchmarkContainer 
      :numberOfElements=numberOfElements
    />
  </div>
</template>

<script>
import BenchmarkContainer from './BenchmarkContainer.vue'

export default {
  name: 'Benchmark',
  components: {
    BenchmarkContainer
  },
  data: function() {
    return {
      numberOfElements: 0
    }
  },
  methods: {
    add1000Elements: function () {
      this.numberOfElements = 10000
    },
    remove1000Elements: function() {
      this.numberOfElements = 0
    }
  },
}
</script>
