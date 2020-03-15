<template>
  <div class="benchmark">
    <button v-on:click="addDivs">addDivs</button>
    <button v-on:click="editDivs">addDivs</button>
    <button v-on:click="removeDivs">removeDivs</button>

    <BenchmarkContainer 
      :selectedTest=selectedTest
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
      selectedTest: '',
    }
  },
  methods: {
    addDivs: function () {
      this.selectedTest = 'add'
    },
    editDivs: function() {
      this.selectedTest = 'edit'
    },
    removeDivs: function() {
      this.selectedTest = 'remove'
    },
  },
}
</script>
