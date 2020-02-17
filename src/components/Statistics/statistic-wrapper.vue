<template>
  <div class="small">
    
    <line-chart :chart-data="datacollection ? datacollection : {}" :options="options"></line-chart>
    <button @click="fillData()">Randomize</button>
  </div>
</template>

<script>
  import LineChart from '@/components/Statistics/statistic'

  export default {
    components: {
      LineChart
    },
    data () {
      return {
        datacollection: null,
        options: {
            legend: {
                display: false,
            }
        }
      }
    },
    mounted () {
      this.fillData()
    },
    methods: {
      fillData () {
        this.datacollection = {
          labels: ['num1', 'num2', 'num3'],
          datasets: [{
            //label: '# of Votes',
            data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt()],
            backgroundColor: [
                '#fda152',
                '#3c1c93',
                '#68c0ff',
            ],
//                    borderColor: [
//                        'rgba(255, 99, 132, 1)',
//                        'rgba(54, 162, 235, 1)',
//                        'rgba(255, 206, 86, 1)',
//                    ],
            borderWidth: 0,
        }]
        }
      },
      getRandomInt () {
        return Math.floor(Math.random() * (50 - 5 + 1)) + 5
      }
    }
  }
</script>

<style>


  .small{
      height: 300px;
      width: 300px;
  }
</style>