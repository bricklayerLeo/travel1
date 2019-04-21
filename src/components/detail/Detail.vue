<template>
  <div>
   <Banner></Banner>
    <Header></Header>
    <div class="content"></div>
  </div>
</template>

<script>
import Banner from './subcomponents/Banner'
import Header from './subcomponents/Header'
export default {
  name: 'Detail',
  components: {
   Banner,
   Header
  },
  data () {
    return {
     
    }
  },
  
}
</script>

<style lang="stylus" scoped>
 .content
    height: 50rem
</style>
