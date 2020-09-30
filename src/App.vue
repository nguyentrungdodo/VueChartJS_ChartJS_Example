<template>
  <div class="small">
    <!-- <line-chart :chartData="datacollection" :options="dataoptions" ></line-chart> -->
    <LineChart  :labels="labels" :datasets="datasets" :beginAtZero="true"/>
    <BubbleChart />
    <RadarChart />
    <BarChart />
    <PieChart />
    <DoughnutChart />
    <MixtypeChart />
    <ScatterChart />
    <PolarAreaChart />
    <button @click="fillData()">Fill Data</button>
  </div>
</template>

<script>
  import LineChart from './components/LineChart'
  import BubbleChart from './components/BubbleChart.vue'
  import RadarChart from './components/RadarChart.vue'
  import BarChart from './components/BarChart.vue'
  import PieChart from './components/PieChart.vue'
  import DoughnutChart from './components/DoughnutChart.vue'
  import MixtypeChart from './components/MixtypeChart.vue'
  import ScatterChart from './components/ScatterChart.vue'
  import PolarAreaChart from './components/PorlarAreaChart.vue'


  export default {
    components: {
      LineChart, BubbleChart, RadarChart, BarChart, PieChart, DoughnutChart, MixtypeChart, ScatterChart, PolarAreaChart
    },
    data () {
      return {
        datacollection: null,
        dataoptions: null,
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Fancy'],
        datasets: [{
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
                data: [75,59,80,81,56]
            },
            {
                label: '# of Votes',
                data: [0, 2, 4, 6, 7, 9],
                backgroundColor: [
                    'rgba(255, 99, 132, 0.2)',
                    'rgba(54, 162, 235, 0.2)',
                    'rgba(255, 206, 86, 0.2)',
                    'rgba(75, 192, 192, 0.2)',
                    'rgba(153, 102, 255, 0.2)',
                    'rgba(255, 159, 64, 0.2)'
                ],
                borderColor: [
                    'rgba(255, 99, 132, 1)',
                    'rgba(54, 162, 235, 1)',
                    'rgba(255, 206, 86, 1)',
                    'rgba(75, 192, 192, 1)',
                    'rgba(153, 102, 255, 1)',
                    'rgba(255, 159, 64, 1)'
                ],
                borderWidth: 1
            }
          ],
      }
    },
    mounted () {
       this.fillData()
    },
    methods: {
      fillData () {
        this.datacollection = {
           labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Fancy'],
            datasets: [{
                showLine: true, // show line or not for only one datashet

                label: "My First Data", //label of the line

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
                data: [75,59,80,81,56,55,40]
            },
            {
                label: '# of Votes',
                data: [0, 2, 4, 6, 7, 9],
                backgroundColor: [
                    'rgba(255, 99, 132, 0.2)',
                    'rgba(54, 162, 235, 0.2)',
                    'rgba(255, 206, 86, 0.2)',
                    'rgba(75, 192, 192, 0.2)',
                    'rgba(153, 102, 255, 0.2)',
                    'rgba(255, 159, 64, 0.2)'
                ],
                borderColor: [
                    'rgba(255, 99, 132, 1)',
                    'rgba(54, 162, 235, 1)',
                    'rgba(255, 206, 86, 1)',
                    'rgba(75, 192, 192, 1)',
                    'rgba(153, 102, 255, 1)',
                    'rgba(255, 159, 64, 1)'
                ],
                borderWidth: 1
            }
            ]
        },
        this.dataoptions = {
              reponsive: false,
              showLines: true, // disable show line for all datasets
              elements: {
                  line: {
                  tension: 0 // disables tension curve all the table
                  },
                  pointRadius : 3 // size of point all the table
              },
              animation: {
                duration: 0 // general animation time
              },
              hover: {
                  animationDuration: 0 // duration of animations when hovering an item
              },
              responsiveAnimationDuration: 0, // animation duration after a resize
              scales: {
              yAxes: [{
                  ticks: {
                      // data reverse upside down or not
                      reverse: true,
                      //begin with zero or not
                      beginAtZero: true
                  }
              }]
            }
        }
      },
      // getRandomInt () {
      //   return Math.floor(Math.random() * (50 - 5 + 1)) + 5
      // }
    }
  }
</script>

<style>
  .small {
    max-width: 600px;
    margin:  150px auto;
  }
</style>