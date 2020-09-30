<script>
 import { mixins, Scatter } from 'vue-chartjs'
 const { reactiveProp } = mixins

  export default {
    extends: Scatter,
    mixins: [reactiveProp],
    props: {
        // labels: {
        //     type: Object,
        //     default() {
        //        return ['Strength','Skill','Health','Speed','Luck']
        //     }
        // },
        datasets: {
            type: Object,
            default() {
                return [
                        {
                            label: 'Scatter Dataset',
                            data: [{
                                x: -10,
                                y: 0
                            }, {
                                x: 0,
                                y: 10
                            }, {
                                x: 10,
                                y: 5
                            }]
                       }
                ]
            }
        },
        reponsive:{
            type: Boolean,
            default: true
        },
        showLine: {
            type: Boolean,
            default: true
        },
        tension: {
            type: Number,
            default: 0.1
        },
        pointRadius: {
            type: Number,
            default: 3
        },
        animationDuration: {
            type: Number,
            default: 0.5
        },
        hoverAnimationDuration: {   
            type: Number,
            default: 0.3
        },
        responsiveAnimationDuration: {
            type: Number,
            default: 0.3
        },
        beginAtZero: {
            type: Boolean,
            default: false
        }
    },
    data() {    
        return { 
            datacollection:{
                // labels: this.labels,
                datasets: this.datasets
            },
            options: {
                scales: {
                    xAxes: [{
                    type: 'linear',
                    position: 'bottom'
                    }]  
                }
            }
        }
    },
    mounted () {
      this.renderChart(this.datacollection, this.options)
    }
  }
</script>