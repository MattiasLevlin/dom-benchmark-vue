<script>
export default {
  name: 'BenchmarkContainer',
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
  watch: {
      selectedTest: {
        handler (value) {
          this.selectedTest = value;
        }
      }
  },
  props: {
    selectedTest: String,
  }
}
</script>