<template>
  <div class="topnavAndBanner">
    <Topnav/>
    <div class="banner">

      <h1 class="bue1">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-icon-b"></use>
        </svg>
        Bue UI
      </h1>
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
      <div class="icon-border">
        <ul>
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
    <span class="rightBox"></span>

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
  overflow-x: hidden;
  background: linear-gradient(180deg, rgba(255, 255, 255, 1) 0%, rgba(243, 241, 240, 1) 100%, rgba(100, 50, 170, 0) 100%);
>.rightBox{

  @media (min-width: 1200px) {

    width: 350px;
    height: 410px;
    right: 200px;
    bottom: 150px;
    position: fixed;
    background-size: 100%;
    background-image: url("../assets/man.png");
  }
}
}

.icon-border {
  margin: 40px 0;
  width: 300px;
  display: flex;
  @media (min-width: 600px) {
    width: 600px;
  }
  @media (min-width: 800px) {
    width: 800px;
  }

  > ul {
    border-top: 1px solid lightgrey;
    display: flex;
    flex-wrap: wrap;
    font-size: 6px;

    > li {
      display: grid;
      justify-content: start;
      align-content: space-between;
      grid-template-areas:
        "icon title"
        "icon text";
      grid-template-columns: 50px auto;
      grid-template-rows: 20px auto;

      > svg {
        grid-area: icon;
      }

      > h3 {
        margin-top: 20px;
        grid-area: title;
        font-size: 18px;
      }

      > p {
        margin-top: 23px;
        grid-area: text
      }

    }
  }

  .icon2 {
    padding-top: 20px;
    height: 60px;
    width: 60px;
  }
}

.banner {
  padding-top: 130px;
  height: 100vh;
  display: flex;
  color: rgba(2, 39, 61);
  justify-content: center;
  align-items: center;
  flex-direction: column;
  @media (min-width: 600px) {
    padding-top: 150px;
    padding-left: 200px;
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
    flex-direction: column;
  }



  > .bue1 {
    font-size: 60px;
    @media (min-width: 600px) {
      font-size: 80px;
    }
  }

  > .bue2 {
    font-size: 20px;
    @media (min-width: 600px) {
      font-size: 40px;
    }
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
      padding: 10px 60px;
      @media (min-width: 600px) {
        padding: 10px 150px;
      }

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