<template lang="html">
  <div class="">
    <chart-component :energyData="energyData"></chart-component>
  </div>

</template>

<script>
import ChartComponent from './components/Chart.vue'
export default {
  data(){
    return {
      energyData: []
        }
    },
    mounted(){
      fetch("https://api.carbonintensity.org.uk/generation")
      .then(data => data.json())
      .then(responseData => {
        this.energyData = [['Fuel', 'Percent'], ...this.filterData(responseData.data.generationmix)]
      })
    },
  components: {
    "chart-component": ChartComponent
  },
  methods: {
    filterData: function(data){
      return data.map(function(item){
        const newDataItem = []
        newDataItem[0] = item["fuel"]
        newDataItem[1] = item["perc"]
        return newDataItem
      })
    }
  }
}
</script>

<style lang="css" scoped>
</style>
