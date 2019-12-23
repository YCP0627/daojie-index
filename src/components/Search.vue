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
                <div class="serach-ad">免费发布服务</div>
            </div>
            <div class="hot-con" v-show="!isScroll">
                <span>大家都在搜：</span>
                <ul>
                    <li>开荒保洁</li>
                    <li>擦玻璃</li>
                    <li>油烟机清洗</li>
                    <li>化妆</li>
                    <li>窗帘清洗</li>
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
            isScroll: false
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
.hot-con li {
    margin-left: 30px;
}
</style>