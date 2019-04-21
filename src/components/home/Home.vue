<template>
<div> 
<home-header ></home-header>
<home-swiper :list="swiperList"></home-swiper>
<home-icon :list="iconList"></home-icon>
<home-recommend :list="recommendList"></home-recommend>
<home-weekend :list="weekendList"></home-weekend>
 </div>
   
</template>

<script>
import HomeHeader from './subcomponents/Header'
import HomeSwiper from './subcomponents/Swiper'
import HomeIcon from './subcomponents/Icon'
import HomeRecommend from './subcomponents/recommend'
import HomeWeekend from './subcomponents/Weenkend'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
    name:'home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcon,
        HomeRecommend,
        HomeWeekend
        },
        data(){
            return{
              lastcity:this.city,
              swiperList:[],
              iconList: [],
              recommendList: [],
              weekendList: []

            }
        },
         computed: {
    ...mapState(['city'])
        },
        methods:{
            getHomeInfo () {
              axios.get('/api/index.json?city='+this.city)
              .then(this.getHomeInfoSucc)
            },
            getHomeInfoSucc(res){
                res = res.data
                if(res.ret && res.data){
                    const data = res.data
                  
                    this.swiperList = data.swiperList
                    this.iconList = data.iconList
                    this.recommendList = data.recommendList
                    this.weekendList = data.weekendList
                }
            }
        },
    mounted(){
        this.lastcity=this.city
         this.getHomeInfo ()
         
        },
        activated(){
            if(this.lastcity !== this.city){
                this.lastcity = this.city
                this.getHomeInfo ()
            }
            
        }
}
</script>

<style scoped>

</style>

