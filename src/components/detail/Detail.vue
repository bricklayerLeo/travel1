<template>
  <div>
   <Banner></Banner>
    <Header></Header>
    <List :list='list'></List>
    <div class="content"></div>
  </div>
</template>

<script>
import Banner from './subcomponents/Banner'
import Header from './subcomponents/Header'
import List from './subcomponents/List'
export default {
  name: 'Detail',
  components: {
   Banner,
   Header,
   List
  },
  data () {
    return {
     list:[
     {title:'成人票',children:[{title:'成人三馆联票',children:[{title:'成人三馆联票 - 五一专卖店销售'}]},{title:'成人五馆联票 '}]},
     {title:'学生票'},
     {title:'儿童票'},
     {title:'特惠票'}
     ]
    }
  },
  
}
</script>

<style lang="stylus" scoped>
 .content
    height: 50rem
</style>
