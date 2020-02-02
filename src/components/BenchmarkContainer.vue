<script>

export default {
  name: 'BenchmarkContainer',
  render (createElement) {
      return createElement('div',
      Array.apply(null, { length:
        this.$props.numberOfElements
      }).map(() => {
          return createElement('div', 'DOM')
      }))
  },
  watch: {
      numberOfElements: {
          handler (val) {
              this.numberOfElements = val;
          }
      }
  },
  props: {
    numberOfElements: Number
  }
}
</script>
