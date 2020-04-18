<template>
  <div class="benchmark">
    <p>Using v-for</p>
      <button @click="addDiv()">1 addDiv</button>
      <button @click="editOneDiv()">2 editOneDiv</button>
      <button @click="editAllDiv()">3 editAllDiv</button>
      <button @click="removeOneDiv()">4 removeOneDiv</button>
      <button @click="removeAllDiv()">5 removeAllDiv</button>
      {{ randomText }}
          <p>Using array.map()</p>
    <button
      v-on:click="add1000Elements"
    >
      Add 10,000 elements
    </button>
    <button
      v-on:click="remove1000Elements"
    >
      Remove 10,000 elements
    </button>
    <BenchmarkContainer 
      :numberOfElements=numberOfElements
      :startTimerArrayMap=startTimerArrayMap
    />
        <div
          id="container"
          v-for="i in divToCreate"
          v-bind:key="i"
          v-html="htmlxc(i)"
          :ref="i"
        >
        <p>Div{{ i }}</p>
    </div>
  </div>
</template>

<script>
/* eslint-disable no-console */
import BenchmarkContainer from './BenchmarkContainer.vue'

export default {
  name: 'Benchmark',
  components: {
    BenchmarkContainer
  },
  data: function() {
    return {
      divToCreate: 0,
      startTimer: null,
      startTimerArrayMap: null,
      stopTimer: null,
      numberOfElements: 0,
      asdf3: 1,
      randomText: 'asd'
    }
  },
  methods: {

    htmlxc: function(i) {
      return `<p>Hello ${ i * this.asdf3 } </p>`;
    },

    // 1
    addDiv () {
      this.startTimer = performance.now()
      this.divToCreate = 10000
    },
    // 2
    editOneDiv: function() {
      this.startTimer = performance.now()
      this.$refs[1][0].textContent = Math.random()
      this.randomText = Math.random()
    },
    editAllDiv: function() {
      this.startTimer = performance.now()
      this.asdf3 = Math.random()
    },
    removeOneDiv: function() {
      this.startTimer = performance.now()
      this.divToCreate = this.divToCreate - 1
    },
    removeAllDiv: function() {
      this.startTimer = performance.now()
      this.divToCreate = 0
    },
    add1000Elements: function () {
      this.startTimerArrayMap = performance.now()
      this.numberOfElements = 10000
    },
    remove1000Elements: function() {
      this.startTimerArrayMap = performance.now()
      this.numberOfElements = 0
  },
    updated: function () {
      this.stopTimer = performance.now()
      console.log('Time it took was: ' + (this.stopTimer - this.startTimer) + 'milliseconds')
    },
  },
}
</script>