<template lang="html">
  <GChart type="ColumnChart" :data="energyData" :options="chartOptions"></GChart>
</template>

<script>
import { GChart } from 'vue-google-charts'
import {eventBus} from '../main.js'

export default {
  props: ["energyData"],
  name: "chart",
  components: {
    GChart
  },
  data() {
    return {
      chartOptions: {
        chart: {
          title: 'Energy Generation',
          subtitle: 'Percentage of energy from various sources'
        }
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
