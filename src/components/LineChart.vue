<script>
 import { Line, mixins } from 'vue-chartjs'
 const { reactiveProp } = mixins

  export default {
    extends: Line,
    mixins: [reactiveProp],
    props: {
        labels: {
            type: Object,
            default() {
               return ['demo1','demo2','demo3','demo4','demo5','demo6']
            }
        },
        datasets: {
            type: Object,
            default() {
                return [
                    {
                        showLine: true, // show line or not for only one datashet

                        label: "My Demo Data", //label of the line

                        fill: false, // fill with color or not

                        lineTension: 0.1, // curve tension of line

                        backgroundColor: 'rgba(75,192,192,0.4)',  // color of fill, if fill true
                        
                        borderColor: 'rgba(120,40,192,1)',  //color of line
                        
                        borderCapStyle: 'butt', // 3 options: "butt" || "round" || "square"
                        
                        borderDash: [10,10],    // đường thẳng vẽ bằng khoảng chấm
                        
                        borderDashOffset: 24, // https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset
                        
                        borderJoinStyle: 'mitter',    // 3 options: "bevel" || "round" || "miter"
                        
                        pointBorderColor: 'rgba(75,170,192,1)',   // color border of every point in line
                    
                        pointBackgroundColor: '#fff',    // color of every point in line
                        
                        pointBorderWidth: 2,    // size of point's border
                        
                        pointHoverRadius: 2,    // size of radius when hover
                        
                        pointHoverBackgroundColor: '#f36h24',   // background color point when hover
                        
                        pointHoverBorderWidth: 2,   // border size of point when hover
                        
                        pointRadius: 1,   // size of point  
                        
                        pointHitRadius: 20,   // The pixel size of the non-displayed point that reacts to mouse events.
                        data: [75,59,80,81,56,55]
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
                reponsive: this.reponsive,
                showLines: this.showLine, // disable show line for all datasets
                elements: {
                    line: {
                        tension: this.tension // disables tension curve all the table
                    },
                    pointRadius : this.pointRadius, // size of point all the table
                },
                animation: {
                    duration: this.animationDuration, // general animation time
                    easing: 'linear',
                    // https://www.chartjs.org/docs/latest/configuration/animations.html#easing
                },
                hover: {
                    animationDuration: this.hoverAnimationDuration // duration of animations when hovering an item
                },
                
                responsiveAnimationDuration: this.responsiveAnimationDuration, // animation duration after a resize
                scales: {
                yAxes: [{
                    ticks: {
                        // data reverse upside down or not
                        reverse: this.reverse,
                        //begin with zero or not
                        beginAtZero: this.beginAtZero
                    }
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