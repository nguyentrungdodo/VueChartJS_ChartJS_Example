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
               return ['Strength','Skill','Health','Speed','Luck','Lol']
            }
        },
        datasets: {
            type: Object,
            default() {
                return [
                    {
                       label: 'Gay Powerrrr',
                       backgroundColor : 'rgba(00,255,00,0.1)',
                       borderColor: '#00FF00',
                       borderSkipped: 'bottom',
                       hoverBackgroundColor: 'rgba(00,255,00,0.1)',
                       hoverBorderColor: 'rgba(00,255,00,0.1)',
                       hoverBorderWidth: 1,
                       order: 3,
                       borderWidth: 2,
                       barPercentage: 0.5,
                    //    barThickness: 6,
                    //    maxBarThickness: 8,
                    //    minBarLength: 2,
                       data: [10,20,55,30,40],
                       stack: 'Stack 0',
                       yAxisID: 'first-y-axis'
                    },{
                       label: 'Less Power',
                       backgroundColor : 'rgba(0,255,255,0.1)',
                       borderColor: '#00FFFF',
                       borderWidth: 2,
                       data: [5,10,20,70,80],
                       stack: 'Stack 0',
                       yAxisID: 'second-y-axis'
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
                title: {
                    text: 'Demo Title',
                    display: true,
                    positions: 'top',  // 'top' || 'left' || 'bottom' || 'right'
                    fontSize: 12,
                    fontFamily: "'Helvetica Neue', 'Helvetica', 'Arial', sans-serif",
                    fontColor: '#666',
                    fontStyle: 'bold',
                    padding: 10,
                    lineHeight: 1.2,
                },
                animation: {
                    // duration: this.animationDuration, // general animation time
                    easing: 'easeInOutBounce',

                },
                tooltips: {
                    mode: 'index',
                    intersect: false
                },
                
                responsive: true,
                legend: {
                    display: true,
                    position: 'top',
                    align: 'center',
                    labels: {
                        boxWidth: 40,
                        fontSize: 12,
                        fontstyle: 'normal',
                        fontcolor: '#fff',
                        fontFamily: "'Helvetica Neue', 'Helvetica', 'Arial', sans-serif",
                        padding: 10,

                    },
                },
                scales: {
                    yAxes: [{
                        id: 'first-y-axis',
                        type: 'linear',

                    }, {
                        id: 'second-y-axis',
                        type: 'linear',
                        position: 'right',
                        gridLines: {
                            drawOnChartArea: false
                        }
                    }]
                },
            }
        }
    },
    mounted () {
      this.renderChart(this.datacollection, this.options)
    }
  }
</script>