<script>
  import { Bubble } from 'vue-chartjs'
  export default {
    extends: Bubble,
    data () {
      return {
        datacollection: {
          labels: ['Data'],
          datasets: [
            {
              label: 'Data One',
              backgroundColor: '#f87979',
              pointBackgroundColor: 'white',
              borderColor: 'rgba(0, 0, 0, 0.1)',
              borderWidth: 1,
              pointStyle: 'buble', //'circle'||'cross'||'crossRot'||'dash'||'line'||'rect'||'rectRounded'||'rectRot'||'star'||'triangle'
              pointBorderColor: '#249EBF',
              data: [
                {
                  x: 100,
                  y: 0,
                  r: 10
                },
                {
                  x: 60,
                  y: 30,
                  r: 20
                },
                {
                  x: 40,
                  y: 60,
                  r: 25
                },
                {
                  x: 80,
                  y: 80,
                  r: 50
                },
                {
                  x: 20,
                  y: 30,
                  r: 25
                },
                {
                  x: 0,
                  y: 100,
                  r: 5
                }
              ]
            }
          ]
        },
        options: {
          scales: {
            yAxes: [{
              ticks: {
                beginAtZero: true
              },
              gridLines: {
                display: true
              }
            }],
            xAxes: [ {
              gridLines: {
                display: false
              }
            }]
          },
          legend: {
            display: true
          },
          responsive: true,
          maintainAspectRatio: false
        }
      }
    },
    mounted () {
      this.renderChart(this.datacollection, this.options)
    }
  }
</script>