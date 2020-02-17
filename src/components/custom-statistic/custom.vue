<template>
    <section id="statistics" data-aos="fade-up">
        {{data}}
        <div class="container">
            <h1 class="main-title">tokken allocation</h1>
            <div class="chart-card">
                <canvas id="myChart" width="300px" height="300px"></canvas>
                <span id="chart-legends"></span>
            </div>
        </div>
    </section>
</template>
<script>
import Chart from '@/assets/js/chart.js';
export default {
    data(){
        return{
            chartElm:'',
            // ChartType:'doughnut',
            //data: [1, 1, 1, 1],
            //labels:['num1', 'num2', 'num3', 'num4'],
            backgroundColor: [],
            backgroundColorArray: ['#6d6af6','#f0a561','#7dbef9','#7adac9','#f66a6a', '#da7ad0']     
        }
    },
    props:['ChartType' , 'data' , 'labels'],
    methods:{
        change(){
            this.data.push(10);
            this.labels.push('numb5');
            this.backgroundColor.push('#fd5252');
            this.UpdateChart();
            //this.initChart();
        },
        UpdateChart(){
            this.chartElm.update();
            document.getElementById('chart-legends').innerHTML = this.chartElm.generateLegend();
        },

        randomColors(){
            var res = this.backgroundColorArray.sort(function() {
            return 0.5 - Math.random();
            });
            this.backgroundColor = res.slice(this.backgroundColorArray,this.labels.length);
        },
        initChart(){
            var ctx = document.getElementById('myChart').getContext('2d');
            this.chartElm = new Chart(ctx, {
                type: this.ChartType,
                data: {
                    labels: this.labels,
                    datasets: [{
                        //label: '# of Votes',
                        data: this.data,
                        backgroundColor: this.backgroundColor,
                        borderWidth: 0,
                    }]
                },
                options: {
                    //cutoutPercentage: 80,
                    responsive: false,
                    legend: {
                        display: false
                    },                
                    legendCallback: function (chart) {
                        var sum = 0;
                        var text = [];
                        for (let i = 0; i < chart.data.datasets[0].data.length; i++) {
                            sum += chart.data.datasets[0].data[i];
                        }
                        
                        text += `<ul class="chart-legends">`;

                        for (let i = 0; i < chart.data.datasets[0].data.length; i++) {

                            text += `<li> <div class="span-test" id="item-${i}" style="background-color:${chart.data.datasets[0].backgroundColor[i]}"></div>${chart.data.labels[i]} : ${Math.round(chart.data.datasets[0].data[i]/sum*100 - 0.5)+' %'} 
                            </li>`;
                            //console.log(chart.data.datasets[0].data[i]);
                            //console.log(chart.data.datasets[0].backgroundColor[i]);
                        }
                        //console.log(sum);

                        text += `</ul>`;
                        return text;
                        //console.log(text);
                    },
                    tooltips: {
                        enabled: true,
                        callbacks: {
                            title: function(tooltipItem, data) {
                                return data['labels'][tooltipItem[0]['index']];
                            },
                            label: function(tooltipItem, data) {
                                return data['datasets'][0]['data'][tooltipItem['index']];
                            },
                            afterLabel: function(tooltipItem, data) {
                                var dataset = data['datasets'][0];
                                var percent = Math.round((dataset['data'][tooltipItem['index']] / dataset["_meta"][0]['total']) * 100)
                                return '(' + percent + '%)';
                            }
                        }
                    }
                },
            });
            document.getElementById('chart-legends').innerHTML = this.chartElm.generateLegend();
            },
            
    },
    mounted(){
        this.randomColors();
        this.initChart();
    }
}
</script>
<style lang="scss">
@import "@/components/custom-statistic/custom.scss";
</style>