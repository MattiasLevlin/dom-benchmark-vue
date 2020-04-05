<template>
  <div>
    <div class="benchmark">
      V-FOR
      <button @click="addDiv()">1 addDiv</button>
      <button @click="editOneDiv()">2 editOneDiv</button>
      <button @click="editAllDiv()">3 editAllDiv</button>
      <button @click="removeOneDiv()">4 removeOneDiv</button>
      <button @click="removeAllDiv()">5 removeAllDiv</button>
      {{ randomText }}
    </div>
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

export default {
  name: 'Benchmark',
  data () {
    return {
      divToCreate: 0,
      startTimer: null,
      stopTimer: null,
      asdf3: 1,
      randomText: 'asd'
      // htmlxc: `<p>Message ${i}</p>`
    }
  },
  computed: {
    /* htmlxc: function() {
      return `<h1>Hello ${ Math.random() }</h1>`;
    } */
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
  },
    updated: function () {
      this.stopTimer = performance.now()
      console.log('Time it took was: ' + (this.stopTimer - this.startTimer) + 'milliseconds')
    },
}
</script>
