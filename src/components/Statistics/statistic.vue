

<script>
import { Doughnut, mixins } from 'vue-chartjs'
const { reactiveProp } = mixins

export default {

  extends: Doughnut,
  mixins: [reactiveProp],
  props: ['options', 'chart-data'],
  data: () => {
    return{
      htmlLegend: null
    }
  },
  mounted () {
    // this.chartData is created in the mixin.
    // If you want to pass options please create a local options object
    this.renderChart(this.chartData, this.options);
    this.htmlLegend = this.generateLegend();
    console.log(this.htmlLegend);
  }
}
</script>

<style lang="scss">

</style>