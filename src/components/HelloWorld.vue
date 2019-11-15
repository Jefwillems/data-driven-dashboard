<template>
<div>
  <apexchart v-for="chart in apiData"
             :key="chart.id"
             :width="'500'"
             :type="chart.type"
             :options="chart.options"
             :series="chart.series" />
</div>
</template>

<script>
import VueApexCharts from 'vue-apexcharts';

export default {
  name: 'HelloWorld',
  components: {
    apexchart: VueApexCharts,
  },
  data() {
    return {
      apiData: [
        {
          id: 1,
          type: 'bar',
          options: {
            chart: {
              id: 'chart-1',
            },
            xaxis: {
              categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
            },
          },
          series: [{
            name: 'series-1',
            data: [30, 40, 45, 50, 49, 60, 70, 91],
          }],
        },
        {
          id: 2,
          type: 'line',
          options: {
            chart: {
              id: 'chart-2',
            },
            xaxis: {
              categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
            },
          },
          series: [
            {
              name: 'series-1',
              data: [15, 24, 86, 10, 47, 51, 78, 91],
            },
            {
              name: 'series-2',
              data: [
                Math.round(Math.random() * 15),
                Math.round(Math.random() * 24),
                Math.round(Math.random() * 86),
                Math.round(Math.random() * 10),
                Math.round(Math.random() * 47),
                Math.round(Math.random() * 51),
                Math.round(Math.random() * 78),
                Math.round(Math.random() * 91),
              ],
            },
          ],
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
