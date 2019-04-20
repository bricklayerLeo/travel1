<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
    <city-alphabet></city-alphabet>
    
    
  </div>
</template>

<script>

import CityHeader from './subcomponents/Header'
import CitySearch from './subcomponents/search'
import CityList from './subcomponents/list'
import CityAlphabet from './subcomponents/alphabet'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      
    }
  },
  
}
</script>

<style lang="stylus" scoped>

</style>
