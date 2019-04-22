<template>
  <div>
   <Banner 
      :sightName="sightName"
      :bannerImg="bannerImg"
      :bannerImgs="gallaryImgs"></Banner>
    <Header></Header>
    <List :list='list'></List>
    <div class="content"></div>
  </div>
</template>

<script>
import Banner from './subcomponents/Banner'
import Header from './subcomponents/Header'
import List from './subcomponents/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
   Banner,
   Header,
   List
  },
  data () {
    return {
     list:[],
     sightName:'',
    bannerImg:'',
    gallaryImgs:[],
    id:this.$route.params.id

    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json?id='+this.id)
        .then(this.handleGetDetailInfoSucc)
    },
    handleGetDetailInfoSucc (res) {
      res = res.data
      console.log(res)
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs= data.gallaryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
  
}
</script>

<style lang="stylus" scoped>
 .content
    height: 50rem
</style>
