<template>
  <div>
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list
      :cities="cities"
      :hot="hotCities"
      :letter="letter"
    ></city-list>
    <city-alphabet
      :cities="cities"
      @change="handleLetterChange"
    ></city-alphabet>
  </div>
</template>

<script>

import CityHeader from './subcomponents/Header'

export default {
  name: 'City',
  components: {
    CityHeader,
    
  },
  data () {
    return {
      
    }
  },
  
}
</script>

<style lang="stylus" scoped>

</style>
