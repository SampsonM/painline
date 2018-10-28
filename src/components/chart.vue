<script>
  import {Line} from 'vue-chartjs'

  export default {
    extends: Line,
    data() {
      return {
        mockData: []
      }
    },
    props: ['label', 'mock'],
    mounted () {
      this.gradient = this.$refs.canvas.getContext('2d').createLinearGradient(0, 0, 0, 450)
      this.gradient2 = this.$refs.canvas.getContext('2d').createLinearGradient(0, 0, 0, 450)

      this.gradient.addColorStop(0, 'rgba(255, 0,0, 0.5)')
      this.gradient.addColorStop(0.2, 'rgba(255, 0, 0, 0.285)');
      this.gradient.addColorStop(1, 'rgba(255, 0, 0, 0)');

      this.renderChart({
        labels: this.mockData[0],
        datasets: [
          {
            label: this.label,
            borderColor: '#FC2525',
            pointBackgroundColor: 'white',
            borderWidth: 1,
            pointBorderColor: 'white',
            backgroundColor: this.gradient,
            data: this.mockData[1]
          }
        ]
      }, {responsive: true, maintainAspectRatio: false});
    },
    beforeMount() {
      this.mockData = this.mock.reduce((acc, cur, i, arr) => {
                        acc[0].push(cur.name);
                        acc[1].push(cur.points);
                        return acc;
                      }, [[],[]]);
                      console.log(this.mockData)
    }
  }

</script>
