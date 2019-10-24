<template lang="html">
  <div class="">
    <chart-component></chart-component>
  </div>

</template>

<script>
import ChartComponent from './components/Chart.vue'
export default {
  data(){
    return {

    }
  },
  components: {
    "chart-component": ChartComponent
  }
}
</script>

<style lang="css" scoped>
</style>
