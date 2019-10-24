<template lang="html">
  <GChart type="ColumnChart" :data="energy" :options="chartOptions"></GChart>
</template>

<script>
import { GChart } from 'vue-google-charts'
import {eventBus} from '../main.js'

export default {
  name: "chart",
  components: {
    GChart
  },
  data() {
    return {
      energy: [
        ['Year', 'Sales', 'Expenses', 'Profit'],
        ['2014', 1000, 400, 200],
        ['2015', 1170, 460, 250],
        ['2016', 660, 1120, 300],
        ['2017', 1030, 540, 350]
      ],
      chartOptions: {
        chart: {
          title: 'Company Performance',
          subtitle: 'Sales, Expenses, and Profit: 2014-2017'
        }
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
