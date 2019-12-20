<template>
  <div class="home">
    <Header></Header>
    <div class="header-ad">
      <div class="header-ad-img">
        <a href="https://dop-open.daojia.com/template/h5/index?dopServiceId=&dopChannel=1&serviceType=1625">
        <img src="@/assets/home/qdszm-banner.jpg" alt="">
        </a>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'home',
  components: {
    Header
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
}
</style>
