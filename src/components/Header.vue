<template>
    <div class="header">
        <div class="header-con">
            <div class="city">
                <div class="city-cur">
                    {{ currentCity }}
                </div>
                <dl class="city-change">
                    <dt>[</dt>
                    <dd><a href="javascript:;" @click="changeCity('0')">{{ city[0] }}</a></dd>
                    <dd><a href="javascript:;" @click="changeCity('1')">{{ city[1] }}</a></dd>
                    <dd><a href="javascript:;" @click="changeCity('2')">{{ city[2] }}</a></dd>
                    <dd><a href="//about.daojia.com/changeCity">切换城市</a></dd>
                    <dt>]</dt>
                </dl>
            </div>
            <div class="user-operate">
                <a href="javascript:;">我的订单</a>
                <a href="javascript:;">登录</a>
            </div>            
        </div>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            currentCity: '长沙',
            city:['上海','北京','广州']
        }
    },
    methods: {
        changeCity(index) {
            let item = this.currentCity;
            this.currentCity = this.city[index];
            this.$set(this.city,index,item);
        }
    }
}
</script>

<style>
.header {
    height: 36px;
    line-height: 36px;
    font-size:12px;
    background-color: #f5f5f5;
    border-bottom: 1px solid #f0f0f0;
}
.header-con {
    width: 1150px;
    margin: 0 auto;
}
.city-cur,
.city-change,
.city-change dt,
.city-change dd {
    float: left;
}
.city-cur {
    margin: 0 10px 0 0;
    color: #e6454a;
}
.city-change {
    margin: 0;
}
.city-change,
.city-change a {
    color:#999;
}
.city-change a:hover,
.city-change a:active {
    color: #e6454a;
}
.city-change dd {
    margin: 0 4px;
}
.user-operate {
    float: right;
}
.user-operate a{
    margin: 0 0 0 16px;
}
</style>