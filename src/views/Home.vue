<template>
  <div class="topnavAndBanner">
    <Topnav/>
    <div class="banner">
      <h1 class="bue1">Bue UI</h1>
      <h2 class="bue2">一个很哇塞的 UI 组件库</h2>
      <div class="actions">
        <a href="https://github.com/Brucezhiyu/Bue-UI-1">
          <span>GITHUB</span>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-github"></use>
          </svg>
        </a>
        <router-link to="/doc" class="get-start">
          <span>GET START</span>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-right"></use>
          </svg>
        </router-link>
      </div>
      <ul class="icon-border">
        <li>
        <svg class="icon2" aria-hidden="true">
          <use xlink:href="#icon-Vue"></use>
        </svg>
        <h3>基于 Vue 3</h3>
        <p>骄傲地使用了 Vue 3 Composition API</p>
        </li>
        <li>
        <svg class="icon2" aria-hidden="true">
          <use xlink:href="#icon-typescript"></use>
        </svg>
        <h3>基于 TypeScript </h3>
        <p>源代码采用 TypeScript 书写（非严格检查）</p>
        </li>
        <li>
          <svg class="icon2" aria-hidden="true">
          <use xlink:href="#icon-light"></use>
        </svg>
        <h3>代码易读</h3>
        <p>每个组件的源代码都极其简洁</p>
        </li>
      </ul>
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
.topnavAndBanner {
  overflow: hidden;
  height: 100vh;
  background: linear-gradient(180deg, rgba(255, 255, 255, 1) 0%, rgba(243, 241, 240, 1) 100%, rgba(100, 50, 170, 0) 100%);

}

.icon-border {
  border-top: 1px solid lightgrey;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  >h3 {
    font-size: 40px;
  }
  >p {
    font-size: 6px;
  }

  .icon2 {
    padding-top: 20px;
    height: 60px;
    width: 60px;
  }
}

.banner {
  padding: 150px 80px;
  display: flex;
  color: rgba(2, 39, 61);
  justify-content: flex-start;
  align-items: flex-start;
  flex-direction: column;

  > .bue1 {
    font-size: 80px
  }

  > .bue2 {
    font-size: 40px;
  }

  > .actions {
    display: flex;
    flex-direction: column;
    padding: 50px 0;

    .get-start {
      background: rgba(67, 185, 127);
    }

    a {
      display: flex;
      justify-content: center;
      margin: 10px 0;
      color: white;
      box-shadow: 0 0 8px rgba(0, 0, 0, 0.25);
      background: rgba(2, 39, 61);
      line-height: 32px;
      border-radius: 4px;
      padding: 10px 150px;

      &:hover {
        text-decoration: none;
      }

      .icon {
        padding-left: 5px;
        height: 30px;
        width: 30px;
      }
    }
  }
}
</style>