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
        <ul class="serve-nav-con clearfix">
            <li class="app qr-code">58到家APP
              <div class="qr-code-con">
                <img src="@/assets/home/qr-app-home.png" alt="">
                <span>扫描二维码 安装客户端</span>
              </div>
            </li>
            <li class="gzh qr-code">公众号</li>
            <li class="xcx qr-code">小程序</li>
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
      <div class="com-intro">
        <ul class="intro-con flex">
          <li class="flex">
            <a href="javascript:;"></a>
            <img src="@/assets/home/icon-brand-rz2x.png" alt="">
            <div class="intro-word">
              <h3>3亿美金</h3>
              <p>2015年 完成3亿美金A轮投资</p>
            </div>
          </li>
          <li class="flex">
            <a href="javascript:;"></a>
            <img src="@/assets/home/icon-brand-jt2x.png" alt="">
            <div class="intro-word">
              <h3>2000万家庭</h3>
              <p>致力于为亿万家庭提供标准化到家服务</p>
            </div>
          </li>
          <li class="flex">
            <a href="javascript:;"></a>
            <img src="@/assets/home/icon-brand-ldz2x.png" alt="">
            <div class="intro-word">
              <h3>200万优秀劳动者</h3>
              <p>专业培训的优秀劳动者受到用户好评</p>
            </div>
          </li>                    
        </ul>
      </div>
    </div>
    <div class="cfooter">
      <div class="footer-con">
        <ul class="f-flex our-links">
          <li><a href="">关于我们</a></li>
          <li><a href="">网站地图</a></li>
          <li><a href="">城市地图</a></li>
          <li><a href="">知识产权保护投诉</a></li>
          <li><a href="">隐私政策</a></li>
        </ul>
        <ul class="about-links f-flex">
          <li v-for = "(value,index) in footerLinks" :key="index" @mouseenter="controlShow(index)" :class="{ 'current': isCurrent[index] }">
            {{ value }}
          </li>
        </ul>
        <ul class="about-link">
          <li v-for="(lists,index) in Links" :key="index" v-show="isCurrent[index]"><a href="" v-for="(value,index) in lists" :key="index">{{ value }}</a></li>
        </ul>
        <div class="com-name">天津五八到家生活服务有限公司 及 北京五八到家信息技术有限公司 及 北京五八信息技术有限公司</div>
        <div class="com-remarks">
          ©2017 Daojia.com 58到家版权所有
          <a href="http://www.miitbeian.gov.cn">津ICP备15004920号</a>
          <a href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=12019202000163">
          <span class="gongan"></span>&nbsp;津公网安备 12019202000163号
          </a>
          &nbsp;&nbsp;增值电信业务经营许可证：津B2-20160028&nbsp;&nbsp;知识产权专线：010-60845452-103030
        </div>
      </div>
    </div>
    <div class="open-ad" v-show="isOpen">
      <div class="open-ad-img"><img src="@/assets/home/bb-img-190927.png" alt=""></div>
      <div class="open-ad-close" @click="closeAd()"><img src="@/assets/home/bb-close_50b4ff2.png" alt=""></div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue'
import Search from '@/components/Search.vue'
import ServeList from '@/components/ServeList'
// import Vue from 'vue'

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
      ],
      footerLinks:['热门服务','热门城市','周边城市','友情链接','知识内容'],
      Links:[
        ['上海保洁','上海保姆','上海保姆','上海保姆','上海保姆','上海保姆','上海保姆','上海保姆','上海保姆','上海保姆','上海保姆','上海保姆'],
        ['长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家'],
        ['长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家','长沙58到家'],
        ['服务信息','身高计算器','身高计算器','身高计算器','身高计算器','身高计算器','身高计算器','身高计算器','身高计算器','长沙58到家','长沙58到家','长沙58到家'],
        ['资讯','资讯','资讯','资讯','资讯','资讯','资讯','长沙58到资讯家','长沙58到家','长沙58到家','长沙58到家','长沙58到家']
      ],
      isCurrent:[false,false,false,false,false],
      isOpen: true
    }
  },
  components: {
    Header,
    Search,
    ServeList
  },
  methods: {
    controlShow(index) {
      console.log(index)
      console.log(this.isCurrent)
      for(let i=0; i<this.isCurrent.length; i++) {
        if(i == index) {
          this.$set(this.isCurrent, i, true);
        } else {
          this.$set(this.isCurrent, i, false);
        }
      }
      console.log(this.isCurrent);
    },
    closeAd() {
      this.isOpen = false;
    }
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
.qr-code {
  padding-right: 12px;
}
.serve-nav-con a {
  color:#333;
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
.serve-nav-con li:last-child{
  margin-right: 0px;
}
.serve-nav-con .xcx{
  margin-right: 12px;
}

.gzh ,
.xcx {
  color: #C39869;
}
.app  {
  font-weight: 800;
  color: #E6454A;
  padding-left: 23px;
  background: url('../assets/home/icon_mobi2x_e9ee54d.png') no-repeat left;
  background-size: 20px 20px;
}

.gzh,
.xcx,
.app {
  position: relative;
}
.gzh:after,
.xcx:after,
.app:after {
  content:'';
  display: block;
  height: 3px;
  width: 3px;
  position: absolute;
  right:2px;
  bottom: 17px;
  border-right: .9px solid #C39869;
  border-top: .9px solid #C39869;
  transition: all .1s;
  transform: rotate(135deg)
}
.app:after {
  border-right: .9px solid #E6454A;
  border-top: .9px solid #E6454A;
}
.gzh:hover, .xcx:hover, .app:hover {
  cursor: pointer;
}
.gzh:hover:after, .xcx:hover:after, .app:hover:after {
  transform:rotate(-45deg);
  bottom: 15px;
}
.qr-code-con {
  position: absolute;
  bottom: -165px;;
  width: 140px;
  left:0;
  /* height: 140px; */
  z-index: 8;
  border: 1px solid #ddd;
  color: #333;
  font-size:12px;
  line-height: 10px;
  text-align: center;
  font-weight: 400;
  background-color:#fff;
  padding-bottom: 8px;
}
.qr-code-con:before {
  content: '';
  display: block;
  position: absolute;
  width: 10px;
  height: 10px;
  top: -6px;
  left:50%;
  margin-left: -4px;
  background-color: #fff;
  border-right: 1px solid #ddd;
  border-top: 1px solid #ddd;
  transform: rotate(-45deg)
}
.qr-code-con img {
  width: 100%;
  height: auto;
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
  height: 178px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.nav-list img {
  width: 178px;
  height: 178px;
  transition:all 1s;
  transform-origin: 50% 50%;
}
.con-nav .nav-list img:hover{
  transform: scale(1.1)
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
  width: 100%;
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
.intro-con {
  padding: 30px 0 30px 0;
}
.intro-con li img {
  width: 40px;
  height: 40px;
  margin-right: 40px;
}
.intro-con li{
  width: 366px;
  height: 118px;
  list-style: none;
  border: 1px solid #E4E4E4;
  position: relative;
  justify-content: center;
  align-items: center;
}
.intro-con li a {
  position: absolute;
  width: 366px;
  height: 118px;
  top: 0;
  left: 0;
}
.intro-con li h3 {
  font-size: 18px;
  color: #333;
  line-height: 24px;
  font-weight: 400;
}
.intro-con li p {
  font-family: PingFangSC-Light,"Microsoft YaHei",sans-serif;
  margin-top: -18px;
  font-size: 14px;
}
.intro-word {
  margin-top: -10px;
}
.cfooter {
  width: 100%;
  background-color: #F5F5F5;
  padding: 21px 0;
}
.footer-con {
  width: 1150px;
  margin: 0 auto;
  text-align: center;
  font-size: 12px;
}
.footer-con>div {
  margin: 10px 0;
}
.footer-con li {
  list-style: none;
}
.our-links li {
  padding: 6px 0;
}
.our-links li a{
  display: block;
  padding: 0 35px;
  border-right: 1px solid #ddd;
}
.our-links li:nth-last-child(1) a{
  border-right: 0;
}
.about-links  {
  margin: 20px 0 16px 0;
}

.about-link li{
  padding-bottom: 12px;
}
.about-link li a {
  padding: 0 2px;
}
.about-links > li {
  margin: 0 9px;
  padding: 0 10px;
  height: 30px;
  line-height: 30px;
  background-color: #E5E5E5;
}
.about-links li,
.about-links li a,
.com-name,
.com-remarks,
.com-remarks a,
.about-link li a {
  color: #999;
}
.f-flex {
  display: flex;
  justify-content: center;
}
.about-links .current {
  background-color: #858585;
  color: #fff;
}
.open-ad {
  background-color: rgba(255, 38, 0, .6);
  width: 100%;
  height: 170px;
  position: fixed;
  bottom: 0;
  z-index: 999
}
.open-ad-img {
  position: absolute;
  top: -30px;
  left:50%;
  margin-left: -470px;
  width: 940px;
  opacity: 1.5;
}
.open-ad-close {
  width: 15px;
  height: 15px;
  position: absolute;
  top: 10px;
  right:135px;
}
.open-ad-close:hover {
  cursor: pointer;
}
.open-ad img {
  width: 100%;
  height: auto;
}
/* 清除浮动方案clearfix */
.clearfix:before,
.clearfix:after {
    display: table;
    content: " ";
}
.clearfix:after {
    clear: both;
}
.clearfix{
    *zoom: 1;
}
</style>
