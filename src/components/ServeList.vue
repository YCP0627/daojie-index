<template>
    <div class="serve-list flex">
        <div class="serve-list-img">
            <img :src=serveList.img alt="">
        </div>
        <div class="serve-list-con">
            <div class="title"><a href="">{{ serveList.title}}</a></div>
            <ul class="flex">
                <li v-for="(value,index) in serveList.con" :key="index"><a href="">{{ value }}</a></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'serveList',
    props: {
        serveList: Object
    }
}
</script>

<style>
.serve-list-img {
    width: 90px;
}
.serve-list-img img {
    width: 100%;
    height: auto;
}
.serve-list-con .title a {
    color: #E6454A;
}
.serve-list-con .title a:hover {
    text-decoration: underline;
}
.serve-list-con ul li {
    list-style: none;
}
.serve-list-con li a {
    font-size: 12px;
}

.serve-list {
    width: 391px;
    height: 90px;
    padding: 0 0 40px 0;
}
.serve-list:nth-child(3n) {
    width: 397px;
    margin-left: -30px;
    position: relative;
    right: -30px;
}
</style>

