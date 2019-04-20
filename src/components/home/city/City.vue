<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    
  </div>
</template>

<script>

import CityHeader from './subcomponents/Header'
import CitySearch from './subcomponents/search'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch
  },
  data () {
    return {
      
    }
  },
  
}
</script>

<style lang="stylus" scoped>

</style>
