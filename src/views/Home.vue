<template>
  <div class="home">
    <Header></Header>
    <div class="header-ad">
      <a href="https://dop-open.daojia.com/template/h5/index?dopServiceId=&dopChannel=1&serviceType=1625">
      <img class="header-ad-img" src="@/assets/home/qdszm-banner.jpg" alt="">
      </a>
    </div>
    <Search></Search>
    <div class="serve-nav">
        <ul class="serve-nav-con">
            <li class="app qr-code"><a href="javascript;:">58到家APP</a></li>
            <li class="gzh qr-code"><a href="javascript;:">公众号</a></li>
            <li class="xcx qr-code"><a href="javascript;:">小程序</a></li>
            <li><a href="javascript;:">家政</a></li>
            <li><a href="javascript;:">保姆月嫂</a></li>
            <li><a href="javascript;:">快狗打车</a></li>
            <li><a href="javascript;:">搬家</a></li>
            <li><a href="javascript;:">上门安装</a></li>
            <li><a href="javascript;:">数码维修</a></li>
            <li><a href="javascript;:">房屋装修</a></li>
            <li><a href="javascript;:">汽车</a></li>
            <li><a href="javascript;:">企业后勤</a></li>
        </ul>
    </div>
    <div class="home-contain">
      <div class="con-ad flex">
        <a href="javascript;:">
          <img src="../assets/home/kgdc-banner.jpg" alt="">
        </a>
        <a href="javascript;:">
          <img src="../assets/home/hhrzm-banner.jpg" alt="">
        </a>
      </div>
      <div class="con-nav flex">
        <div class="nav-list" v-for="(list,index) in navLists" v-bind:key = index >
          <img :src=list.img alt="">
          <h3>{{ list.title }}</h3>
          <p>{{ list.con }}</p>
          <a href="javascript:;"></a>
        </div>
      </div>
      <div class="serve-all flex">
        <serve-list v-for="(list,index) in serveLists" v-bind:key = index :serveList=list></serve-list>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue'
import Search from '@/components/Search.vue'
import ServeList from '@/components/ServeList'

export default {
  name: 'home',
  data: function() {
    return {
      navLists: [
        {title:'日常保洁',con:'洁净爱家 精心舒适',img:require('@/assets/home/pic_class_hot_slwx.png')},
        {title:'搬家·拉货',con:'品质保证 价格优惠',img:require('@/assets/home/pic_class_hot_slwx.png')},
        {title:'手机维修',con:'服务专业 方便快捷',img:require('@/assets/home/pic_class_hot_slwx.png')},
        {title:'管道疏通',con:'立即上门 实时响应',img:require('@/assets/home/pic_class_hot_slwx.png')},
        {title:'水路维修',con:'到家服务 快捷安心',img:require('@/assets/home/pic_class_hot_slwx.png')},
        {title:'全部分类',con:'发现更多 到家服务',img:require('@/assets/home/pic_class_hot_slwx.png')}
        ],
      serveLists: [
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
        {title:'家政',con:['日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁','日常保洁'],img:require('@/assets/home/class_item_baojie.jpg')},
      ]
    }
  },
  components: {
    Header,
    Search,
    ServeList
  }
}
</script>

<style>
.header-ad {
  width: 1150px;
  margin: 0 auto;
}
.header-ad-img {
  width: 100%;
  height: auto;
  vertical-align : bottom;
}
.serve-nav {
  width: 1150px;
  margin: 14px auto;
  padding: 5px 0;
  border-bottom: 1px solid #e6454a;
}
.serve-nav-con {
  overflow: hidden;
}
.qr-code {
  padding-right: 12px;
}
.serve-nav-con li{
  float: left;
  list-style: none;
  top: 0;
  left: 0;
  font-size: 14px;
  height: 36px;
  line-height: 36px;
  margin-right: 50px;
}
.serve-nav-con .xcx,
li:last-child{
  margin-right: 0;
}

.gzh a,
.xcx a {
  color: #C39869;
}
.app a {
  font-weight: 800;
  color: #E6454A
}
.app {
  padding-left: 23px;
  background: url('../assets/home/icon_mobi2x_e9ee54d.png') no-repeat left;
  background-size: 20px 20px;
}
.home-contain {
  width: 1150px;
  margin: 0 auto;
}
.flex {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.con-ad a {
  width:566px;
}
.con-ad a img {
  width: 100%;
  height: auto;
}
.nav-list {
  width: 178px;
  text-align: center;
  position: relative;
}
.nav-list img {
  width: 100%;
  height: auto;
}
.nav-list h3 {
  font-size: 16px;
  color:#4D4D4D;
  position: absolute;
  top: 4%;
  left: 50%;
  transform: translateX(-50%);
  font-weight: 400;
}
.nav-list p {
  font-size: 12px;
  position: absolute;
  color: #999;
  top: 23%;
  left: 44%;
  transform: translateX(-40%);
}
.nav-list a {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
}
.con-ad,
.con-nav {
    margin-bottom: 14px;
}
</style>
