<template>
  <div id="app">
    <div class="header">
    <myHeader :sellers="sellers"> </myHeader>
    </div>
    <div class="tab">
      <div class="tab-item">
         <router-link :to="{ path: '/goods'}">商品</router-link>
      </div>
      <div class="tab-item">
        <router-link :to="{ path: '/ratings'}">评论</router-link>
      </div>
      <div class="tab-item">
        <router-link :to="{ path: '/sellers'}">商家</router-link>
      </div>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
import myHeader from 'components/header/MyHeader.vue'
// const ERR_OK = 0 // 状态吗
export default {
  name: 'app',
  data () {
    return {
      sellers: {
        avatar: 'http://imgsrc.baidu.com/imgad/pic/item/267f9e2f07082838b5168c32b299a9014c08f1f9.jpg',
        name: '田老师大排档',
        deliveryTime: '20',
        description: '蜂鸟送达',
        supports: [
          {
            type: '0',
            description: '满20减5'
          },
          {
            type: '1',
            description: '单人套餐'
          }
        ]
      }
    }
  },
  components: {
    myHeader
  }
}
</script>

<style>
body{
  margin:0;
}
/* flex */
.tab{
  display: flex;
  width:100%;
  height: 40px;
  line-height: 40px;
  position:relative;
  border-bottom:1px solid rgba(7,17,27,0.1);
}
/*.tab:after{
  display: block;
  position: absolute;
  left: 0;
  bottom: 0;
  border-bottom:1px solid rgba(7,17,27,0.1);
  content: ""
}*/
.tab .tab-item{
  flex:1;
  text-align: center;
}
.tab .tab-item a{
  display: block;
  text-decoration: none;
  color:rgb(77, 85, 93);
  font-size: 14px;
}
.tab .tab-item .router-link-active{
  color:rgb(240, 20, 20);
}
</style>
