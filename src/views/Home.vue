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
            <li class="app qr-code" @mouseenter="isCode=true">
              58到家APP
              <div class="qr-code-con app-code" @mouseenter="isCode=!isCode" v-show="isCode">
                <img src="@/assets/home/qr-app-home.png" alt="">
                <span>扫描二维码 安装客户端</span>
              </div>
            </li>
            <li class="gzh qr-code"  @mouseenter="isCode=true">
              公众号
              <ul class="qr-code-con gzh-code flex" @mouseenter="isCode=!isCode" v-show="isCode">
                <li>
                  <img src="@/assets/home/qr-wx-daojia.jpg" alt="">
                  <div class="gzh-intro">
                    <p>【58到家公众号】</p>
                    <p>重要提醒不错过</p>
                    <p>手机操作更简单</p>
                  </div>
                </li>
                <li>
                  <img src="@/assets/home/qr-wx-jiazheng.jpg" alt="">
                  <div class="gzh-intro">
                    <p>【58家政订阅号】</p>
                    <p>干货福利通通有</p>
                    <p>最新活动抢先知</p>
                  </div>
                </li>
                <li>
                  <img src="@/assets/home/qr-wx-jiuye.jpg" alt="">
                  <div class="gzh-intro">
                    <p>【58家政就业号】</p>
                    <p>阿姨上户更轻松</p>
                    <p>简历创建更便捷</p>
                  </div>
                </li>
                <li>
                  <img src="@/assets/home/qr-wx-ayi.jpg" alt="">
                  <div class="gzh-intro">
                    <p>【阿姨一点通】</p>
                    <p>技能提升好帮手</p>
                    <p>厨艺经验交流多</p>
                  </div>
                </li>                                              
              </ul>  
            </li>
            <li class="xcx qr-code"  @mouseenter="isCode=true">
              小程序
              <div class="qr-code-con xcx-code" @mouseenter="isCode=!isCode" v-show="isCode">
                <img src="@/assets/home/qr-xcx.jpg" alt="">
                <span>扫码即用 无需下载</span>
              </div>              
            </li>
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
          <a href="http://www.miitbeian.gov.cn">  津ICP备15004920号  </a>
          <a href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=12019202000163">津公网安备 12019202000163号</a>
          &nbsp;&nbsp;增值电信业务经营许可证：津B2-20160028&nbsp;&nbsp;知识产权专线：010-60845452-103030
        </div>
      </div>
    </div>
    <div class="open-ad" v-show="isOpen">
      <div class="open-ad-img">
        <img src="@/assets/home/bb-img-190927.png" alt="">
        <div class="open-ad-close" @click="closeAd()"><img src="@/assets/home/bb-close_50b4ff2.png" alt=""></div>
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
      isOpen: true,
      isCode: true,
    }
  },
  components: {
    Header,
    Search,
    ServeList
  },
  methods: {
    controlShow(index) {
      for(let i=0; i<this.isCurrent.length; i++) {
        if(i == index) {
          this.$set(this.isCurrent, i, true);
        } else {
          this.$set(this.isCurrent, i, false);
        }
      }
    },
    closeAd() {
      this.isOpen = false;
    }
  }
}
</script>

<style>
@import '../assets/css/home.css'
</style>
