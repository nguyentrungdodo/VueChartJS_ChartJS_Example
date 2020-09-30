<script>
 import { Bar, mixins } from 'vue-chartjs'
 const { reactiveProp } = mixins

  export default {
    extends: Bar,
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
                       type: 'bar',
                       label: 'Gay Power',
                       backgroundColor : 'rgba(00,255,00,0.1)',
                       borderColor: '#00FF00',
                       borderWidth: 2,
                       data: [10,20,55,30,40]
                    },{
                       type: 'line',
                       label: 'Less Power',
                       backgroundColor : 'rgba(0,255,255,0.1)',
                       borderColor: '#00FFFF',
                       borderWidth: 2,
                       data: [5,100,20,70,80]
                    },
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
            }
        }
    },
    mounted () {
      this.renderChart(this.datacollection, this.options)
    }
  }
</script>