<script>
 import { Radar, mixins } from 'vue-chartjs'
 const { reactiveProp } = mixins

  export default {
    extends: Radar,
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
                       label: 'Gay Power',
                       fill: false,
                       order: 2,
                       lineTension : 0,
                       spanGaps: false,  // If false, NaN data causes a break in the line.
                       backgroundColor : 'rgba(00,255,00,0.1)', //The line fill color.
                       borderCapStyle: 'butt', // "butt" || "round" || "square"
                       borderColor: 'rgba(75,192,192,0.4)', //The line color.
                    //    borderDash: [10,10], //Length and spacing of dashes
                       borderDashOffset: 0.0, //Offset for line dashes //https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineDashOffset
                       borderJoinStyle: 'mitter', // "bevel" || "round" || "miter"
                       borderWidth: 3, //The line width (in pixels).
                       hoverBackgroundColor: 'rgba(00,255,00,0.1)',
                       hoverBorderColor: 'rgba(00,255,00,0.1)',
                       hoverBorderDash : [0,0],
                       hoverBorderDashOffset : 0,
                       //hoverBorderJoinStyle: 
                       hoverBorderWidth: 1,
                       pointHoverBackgroundColor: 'rgba(00,255,00,0.1)', //Point background color when hovered.
                       pointHoverBorderColor : 'rgba(00,255,00,0.1)', //Point border color when hovered.
                       pointHoverBorderWidth : 2, //Border width of point when hovered.
                       pointHoverRadius: 4, //The radius of the point when hovered.
                       pointRadius: 3,  //The radius of the point shape. If set to 0, the point is not rendered.
                       pointRotation: 20, //The rotation of the point in degrees.
                       pointBackgroundColor: 'rgba(00,255,00,0.1)', //The fill color for points.
                       pointBorderColor : 'rgba(00,255,00,0.1)', //The border color for points.
                       pointBorderWidth : 3, //	The width of the point border in pixels.
                       pointHitRadius : 2,  // The pixel size of the non-displayed point that reacts to mouse events.
                       pointStyle: 'circle', // "circle" || 'cross' || 'crossRot' || 'dash' || 'line' || 'rect' || 'rectRounded' || 'rectRot' || 'star' || 'triangle'
                       
                       data: [10,20,55,30,40]
                    },{
                       label: 'Less Power',
                       order: 1,
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