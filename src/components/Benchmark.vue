<template>
  <div>
    <div class="benchmark">
      <button @click="addDiv()">1 addDiv</button>
      <button @click="editOneDiv()">2 editOneDiv</button>
      <button @click="editAllDiv()">3 editAllDiv</button>
      <button @click="removeOneDiv()">4 removeOneDiv</button>
      <button @click="removeAllDiv()">5 removeAllDiv</button>
    </div>
    <div class="asd">
        <div
          v-for="i in divToCreate"
          v-bind:key="i">
            <p>Div{{ i }}</p>
        </div>
    </div>

  </div>
</template>

<script>

export default {
  name: 'Benchmark',
  data () {
    return {
      divToCreate: 0,
      asd1: null,
      asd2: null
    }
  },
  methods: {
    /* eslint-disable no-console */

    // 1
    addDiv () {
      this.asd1 = performance.now()
      this.divToCreate = 10000
    },
    // 2
    editOneDiv: function() {
      // this.selectedTest = 'edit'
    },
    editAllDiv: function() {

    },
    removeOneDiv: function() {
      this.asd1 = performance.now()
      this.divToCreate = this.divToCreate - 1
    },
    removeAllDiv: function() {
      this.asd1 = performance.now()
      this.divToCreate = 0
    },
  },
    updated: function () {
      this.asd2 = performance.now()
      console.log('Time it took was: ' + (this.asd2 - this.asd1) + 'milliseconds')
    },
    render: function (createElement) {
    let divToCreate = []
    if (this.selectedTest === 'add') {
      
      for (var i = 0; i < 10000; i += 1) {
          divToCreate.push(<div
            class="benchmark"
            id={i}
          >
              <p>asd</p>
          </div>)
      }
    }
      return createElement(divToCreate)
  },
}
</script>
