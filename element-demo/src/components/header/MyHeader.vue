<template>
  <div class="myHeader">
    <div class="content-wrapper">
      <div class="avatar">
        <img :src="sellers.avatar" width="64" height="64">
      </div>
      <div class="conetnt">
        <div class="title">
          <span class="brand"></span>
          <span class="name">{{sellers.name}}</span>
        </div>
        <div class="description">{{sellers.description}}/{{sellers.deliveryTime}}分钟送达</div>
        <div v-if="sellers.supports" class="support">
          <span class="icon" :class="classMap[sellers.supports[0].type]"></span>
          <span class="text">{{sellers.supports[0].description}}</span>
        </div>
      </div>
    </div>
    <div class="bullentin-wrapper"></div>
  </div>
</template>
<script>
export default {
  props: {
    sellers: { // 父子组件传递值
      type: Object
      // default: {} // 这里可以指定默认值
    }
  },
  name: 'myHeader',
  data () {
    return {

    }
  },
  created () {
    this.classMap = ['img1', 'img2', 'img3']
  }
}
</script>
<style>
.myHeader{
  color:#fff;
  background:#000;
}
.content-wrapper{
  padding:24px 12px 18px 24px;
  font-size: 0;  /*为了让内嵌块元素在一起的时候没有间隙*/
}
.content-wrapper .avatar ,.content-wrapper .conetnt{
  display: inline-block;
  font-size: 14px;
}
.content-wrapper .conetnt{
  margin-left: 16px;
}
.content-wrapper .conetnt .title{
  margin: 2px 0 8px 0;
}
.brand{
  width: 30px;
  height: 18px;
  display: inline-block;
  background-size: 30px 18px;
  background-repeat: no-repeat;
  background-image: url(http://img3.imgtn.bdimg.com/it/u=957852617,3947337788&fm=26&gp=0.jpg);
  vertical-align: top;
}
.name{
  margin-left: 6px;
  font-size: 16px;
  line-height: 18px;
}
.description{
font-size: 12px;
line-height: 12px;
margin-bottom: 10px;
}
.icon{
  display: inline-block;
  width: 12px;height: 12px;
  margin-right: 4px;
  background-size: 12px 12px;
  background-repeat: no-repeat;
  /*background-image: 这是好多种情况的 */
}
.icon.img1{
  background-image:url(http://img1.imgtn.bdimg.com/it/u=515973783,875625772&fm=26&gp=0.jpg);
}
.icon.img2{
  background-image:url(http://img1.imgtn.bdimg.com/it/u=414623249,873619310&fm=26&gp=0.jpg);
}
.icon.img3{
  background-image:url(http://img2.imgtn.bdimg.com/it/u=1940632570,553653082&fm=26&gp=0.jpg);
}
</style>
