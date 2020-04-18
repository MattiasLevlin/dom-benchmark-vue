<script>
/* eslint-disable no-console */
export default {
  name: 'BenchmarkContainer',
  render (createElement) {
      return createElement('div',
      Array.apply(null, { length:
        this.$props.numberOfElements
      }).map((e, i) => {
          return createElement('div', 'div #' + this.dogs(i, this.$props.dogsz))
      }))
  },
  watch: {
      numberOfElements: {
          handler (val) {
              this.numberOfElements = val;
          }
      },
      dogsz: {
        handler (val) {
          this.dogsz = val;
        }
      }
  },
    updated: function () {
      this.stopTimer = performance.now()
      console.log('Time it took was: ' + (this.stopTimer - this.$props.startTimerArrayMap) + 'milliseconds')
    },
  methods: {
    dogs: function(i, dogsz) {
        return dogsz * i
    },
  },
  props: {
    numberOfElements: Number,
    startTimerArrayMap: null,
    dogsz: Number,
  }
}
</script>
