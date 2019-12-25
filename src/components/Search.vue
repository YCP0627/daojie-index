<template>
    <div :class="{ 'scroll-search': isScroll }">
        <div class="search">
            <div class="search-con">
                <div class="search-logo">
                    <a href="javascript:;">
                        <img class="search-logo-img" src="@/assets/home/logo_dj.png" alt="">
                    </a>
                </div>
                <div class="search-input">
                    <input class="input-con" type="text" placeholder="请输入服务关键字来寻找服务">
                    <button class="search-button">搜服务</button>
                </div>
                <div class="serach-ad" @mouseenter="isShow=true">
                    免费发布服务
                    <div class="bus-code" @mouseenter="isShow=!isShow" v-show="isShow">
                        <img src="@/assets/home/qr-app-home.png" alt="">
                        <span>扫描二维码 安装客户端</span>
                    </div>                      
                </div>
            </div>
            <div class="hot-con" v-show="!isScroll">
                <span>大家都在搜：</span>
                <ul>
                    <li><a>开荒保洁</a></li>
                    <li><a>擦玻璃</a></li>
                    <li><a>油烟机清洗</a></li>
                    <li><a>化妆</a></li>
                    <li><a>窗帘清洗</a></li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'header',
    data: function() {
        return {
            isScroll: false,
            isShow: true
        }
    },
    methods: {
        scrollHander:function() {
            // let scrollHeight = document.querySelector('.search').scrollTop;
            if((document.documentElement.scrollTop > 90)) {
                this.isScroll = true;
            } else {
                this.isScroll = false;
            }
        }
    },
    mounted () {
    window.addEventListener('scroll', this.scrollHander)
    }
}
</script>

<style>
.search {
    width: 1150px;
    height: 78px;
    margin: 0 auto;
    position: relative;
    padding-top: 10px;
    font-size: 14px;
}
.scroll-search {
    width: 100%;
    position: fixed;
    top: 0;
    box-shadow: 0 0 4px 0 rgba(0,0,0,.2);
    background-color: rgba(255,255,255,.8);
    z-index: 999;
}
.scroll-search .search {
    padding-top: 0;
}
.search-con {
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.search-logo {
    width: 160px;
}
.search-logo-img {
    width: 100%;
    height: auto;
    vertical-align : bottom;
}
.search-input {
    display: flex;
    margin-left: -50px;
}
.input-con {
    width: 330px;
    height: 20px;
    /* line-height: 20px; */
    padding: 9px 10px 9px 36px;
    border: 2px solid #e6454a;
    outline: none;
    background: url('../assets/home/icon_zoom2x_d801627.png') no-repeat 12px center;
    background-size: 20px;
}
.search-button {
    width: 80px;
    height: 42px;
    cursor: pointer;
    border: none;
    outline: none;
    background-color: #e6454a;
    color: #fff;
}
.search-button:hover {
    background-color:crimson;
}
.serach-ad {
    height: 30px;
    line-height: 30px;
    padding-left: 24px;
    background: url('../assets/home/icon_edit2x.gif') no-repeat  0 1px;
    background-size: 24px;
    color: #C39869;
}
input::-webkit-input-placeholder,
  textarea::-webkit-input-placeholder {
    /* WebKit browsers */
    color: #999;
  }

.hot-con {
    position: absolute;
    color: #999;
    font-size: 12px;
    bottom: -5px;
    left: 30%;
}
.hot-con ul,
.hot-con li {
    display: inline;
    padding: 0;
}
.hot-con li a {
    color: #999;
}
.hot-con li a:hover {
    color: #e6454a;
}
.hot-con li {
    margin-left: 30px;
}
.serach-ad {
    position: relative;
}
.bus-code {
  position: absolute;
  border: 1px solid #ddd;
  color: #333;
  font-size:12px;
  line-height: 10px;
  text-align: center;
  font-weight: 400;
  padding-bottom: 8px;
  background-color:#fff;
  opacity: 0;
  z-index: 10;
  transition: all 200ms;
  transform: translateY(0) scale(0);
  width: 140px;
  bottom: -165px;;
  left:-12px;
  z-index: 8;
}
.bus-code img {
    width: 100%;
    height: auto;
}
.bus-code:before {
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
  transform: rotate(-45deg);    
}
.serach-ad:hover .bus-code{
  opacity: 1;
  transform-origin: 50% 0;
  transform: translateY(0) scale(1);
}
</style>