<script>
/* eslint-disable no-console */
export default {
  name: 'BenchmarkContainer',
  render (createElement) {
      return createElement('div',
      Array.apply(null, { length:
        this.$props.numberOfElements
      }).map((e, i) => {
          return createElement('div', 'div #' + i)
      }))
  },
  watch: {
      numberOfElements: {
          handler (val) {
              this.numberOfElements = val;
          }
      }
  },
  updated: function () {
      this.stopTimer = performance.now()
      console.log('Time it took was: ' + (this.stopTimer - this.$props.startTimerArrayMap) + 'milliseconds')
    },
  props: {
    numberOfElements: Number,
    startTimerArrayMap: null,
  }
}
</script>
