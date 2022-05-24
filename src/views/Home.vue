<template>
  <div class="topnavAndBanner">
    <Topnav/>
    <div class="banner">
      <h1>guluUI</h1>
      <h2>一个很哇塞的 UI 框架</h2>
      <p class="actions">
        <a href="https://github.com/Brucezhiyu/Bue-UI-1">Github</a>
        <router-link to="/doc">开始</router-link>
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import Topnav from '../components/Topnav.vue';

export default {
  components: {Topnav}
};
</script>

<style lang="scss" scoped>
.topnavAndBanner{
  height: 100vh;
  background: linear-gradient(180deg, rgba(255,255,255,1) 0%, rgba(243,241,240,1) 100%, rgba(100,50,170,0) 100%);

}
.banner {
  padding: 100px 0;
  display: flex;
  color: rgba(2,39,61);
  justify-content: center;
  align-items: center;
  flex-direction: column;
  > .actions{
    padding: 8px 0;
    a {
      margin:0 8px;
      color: white;
      background: rgba(67,185,127);
      display: inline-block;
      height: 35px;
      line-height: 28px;
      border-radius: 20px;
      padding: 2px 20px;
    }
  }
}
</style>