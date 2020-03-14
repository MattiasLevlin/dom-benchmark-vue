<template>
  <div class="benchmark">
    <button v-on:click="addEmptyDivs">addEmptyDivs</button>
    <button v-on:click="removeEmptyDivs">removeEmptyDivs</button>
    <button v-on:click="addDivs">addDivs</button>
    <button v-on:click="removeDivs">removeDivs</button>
    <button v-on:click="addEmptySvgs">addEmptySvgs</button>
    <button v-on:click="removeEmptySvgs">removeEmptySvgs</button>
    <button v-on:click="addSvgs">addSvgs</button>
    <button v-on:click="removeSvgs">removeSvgs</button>

    <BenchmarkContainer 
      :numberOfElements=numberOfElements
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
      numberOfElements: 0,
      selectedTest: '',
    }
  },
  methods: {
    // Test 1, 2 empty divs
    addEmptyDivs: function () {
      this.numberOfElements = 10000
      this.selectedTest = 'empty_div'
    },
    removeEmptyDivs: function() {
      this.numberOfElements = 0
      this.selectedTest = 'empty_div'
    },
    // Test 3, 4 nonempty divs
    addDivs: function () {
      this.numberOfElements = 10000
      this.selectedTest = 'nonempty_div'
    },
    removeDivs: function() {
      this.numberOfElements = 0
      this.selectedTest = 'nonempty_div'
    },
    // Test 5, 6 empty svgs
    addEmptySvgs: function () {
      this.numberOfElements = 10000
      this.selectedTest = 'empty_svg'
    },
    removeEmptySvgs: function() {
      this.numberOfElements = 0
      this.selectedTest = 'empty_svg'
    },
    // Test 7, 8 nonempty svgs
    addSvgs: function () {
      this.numberOfElements = 10000
      this.selectedTest = 'nonempty_svg'
    },
    removeSvgs: function() {
      this.numberOfElements = 0
      this.selectedTest = 'nonempty_svg'
    }
  },
}
</script>
