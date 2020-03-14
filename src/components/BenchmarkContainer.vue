<script>
import DivEmpty from './DivEmpty.vue'
import DivNonempty from './DivNonempty.vue'
import SvgEmpty from './SvgEmpty.vue'
import SvgNonempty from './SvgNonempty.vue'

export default {
  name: 'BenchmarkContainer',
  render (createElement) {
      let elementToCreate = null
      if (this.$props.selectedTest == "empty_div") {
        elementToCreate = DivEmpty
      } else if (this.$props.selectedTest == "nonempty_div") {
        elementToCreate = DivNonempty
      } else if (this.$props.selectedTest == "empty_svg") {
        elementToCreate = SvgEmpty
      } else if (this.$props.selectedTest == "nonempty_svg") {
        elementToCreate = SvgNonempty
      }
      return createElement(
        'div',
        Array.apply(
          null, { 
            length: this.$props.numberOfElements
          }
        ).map(
            () => {
              return createElement(elementToCreate)
            }
        )
      )
  },
  watch: {
      numberOfElements: {
        handler (value) {
            this.numberOfElements = value;
        }
      },
      selectedTest: {
        handler (value) {
          this.selectedTest = value;
        }
      }
  },
  props: {
    numberOfElements: Number,
    selectedTest: String,
  }
}
</script>
