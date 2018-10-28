<script>
  import {Line} from 'vue-chartjs'

  export default {
    extends: Line,
    data() {
      return {
        chartInfo: []
      }
    },
    props: ['label', 'chartData'],
    mounted () {
      this.gradient = this.$refs.canvas.getContext('2d').createLinearGradient(0, 0, 0, 450)
      this.gradient2 = this.$refs.canvas.getContext('2d').createLinearGradient(0, 0, 0, 450)

      this.gradient.addColorStop(0, '#fa09')
      this.gradient.addColorStop(0.2, '#fa02');
      this.gradient.addColorStop(1, 'rgba(255, 0, 0, 0)');

      this.renderChart({
        labels: this.chartInfo[0],
        datasets: [
          {
            label: this.label,
            borderColor: '#fa0',
            pointBackgroundColor: 'white',
            borderWidth: 1,
            pointBorderColor: 'white',
            backgroundColor: this.gradient,
            data: this.chartInfo[1]
          }
        ]
      }, {responsive: true, maintainAspectRatio: false});
    },
    created() {

      this.chartInfo = this.chartData.reduce((acc, cur, i, arr) => {
                          acc[0].push(cur.name);
                          acc[1].push(cur.points);
                          return acc;
                        }, [[],[]]);

      }
      

  }

</script>
