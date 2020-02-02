<script>

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
  props: {
    numberOfElements: Number
  }
}
</script>

<style scoped>
div {
  color: red;
  background: blue;
}
</style>
