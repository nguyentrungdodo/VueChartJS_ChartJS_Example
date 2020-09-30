<script>
 import { mixins, Doughnut } from 'vue-chartjs'
 const { reactiveProp } = mixins

  export default {
    extends: Doughnut,
    mixins: [reactiveProp],
    props: {
        labels: {
            type: Object,
            default() {
               return ['Strength','Skill','Health','Speed','Luck']
            }
        },
        datasets: {
            type: Object,
            default() {
                return [
                    {
                       label: 'Demo Power',
                       backgroundColor : ['#F1C40F','#E67E22','#16E085','#298B9'],
                       borderAlign:'inner',
                       borderColor: '#fff',
                       borderWidth: 2,
                       hoverBackgroundColor: ['#F1C40F','#E67E22','#16E085','#298B9'],
                       hoverBorderColor: '#fff',
                       hoverBorderWidth: 1,
                       data: [10,20,55,30,10]
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
                labels: this.labels,
                datasets: this.datasets
            },
            options: {
                rotation: 100,
                cutoutPercentage: 0, 
                animation: {
                    animateRotate: false,
                    animateScale: true,
                }   
            },
           
        }
    },
    mounted () {
      this.renderChart(this.datacollection, this.options)
    }
  }
</script>