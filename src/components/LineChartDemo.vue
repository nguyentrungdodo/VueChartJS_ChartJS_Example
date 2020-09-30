<script>
 import { Line, mixins } from 'vue-chartjs'
 const { reactiveProp } = mixins

  export default {
    extends: Line,
    mixins: [reactiveProp],
    props: {
      chartData: {
      type:Object,
      require:true
     },
     options: {
      type: Object,
      defautl: null
     }
    },
    data () {
      return {
        datacollection: this.chartData,
        // options: {
        //   scales: {
        //     yAxes: [{
        //       ticks: {
        //         beginAtZero: true
        //       },
        //       gridLines: {
        //         display: true
        //       }
        //     }],
        //     xAxes: [ {
        //       gridLines: {
        //         display: false
        //       }
        //     }]
        //   },
        //   legend: {
        //     display: true
        //   },
        //   responsive: true,
        //   maintainAspectRatio: false
        // }
      }
    },
    mounted () {
      this.renderChart(this.datacollection, this.options)
    }
  }
</script>