<template>
  <div class="layout">
    <Topnav :toggle-menu-button-visible="true" class="nav"/>
    <div class="topnav">
      <div class="logo"></div>
      <div class="menu"></div>
    </div>
    <div class="content">
      <aside v-if="menuVisible">
        <h2>文档</h2>
        <ol>
          <li>
            <router-link to="/doc/intro">介绍</router-link>
          </li>
          <li>
            <router-link to="/doc/install">安装</router-link>
          </li>
          <li>
            <router-link to="/doc/get-started">快速上手</router-link>
          </li>
        </ol>
        <h2>组件列表</h2>
        <ol>
          <li>
            <router-link to="/doc/switch">Switch 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/button">Button 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/dialog">Dialog 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/tabs">Tabs 组件</router-link>
          </li>
        </ol>
      </aside>
      <main>
        <router-view/>
      </main>
    </div>
  </div>
</template>

<script lang="ts">
import Topnav from '../components/Topnav.vue';
import {inject, Ref} from 'vue';

export default {
  components: {Topnav},
  setup() {
    const menuVisible = inject<Ref<boolean>>('menuVisible');
    return {menuVisible};

  }
};
</script>

<style lang="scss" scoped>

main {
  overflow: auto;
}

aside {
  background: white;
  width: 270px;
  padding: 100px 0;
  border-right: 1px solid lightgrey;
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  z-index: 10;

  > h2 {
    margin-bottom: 4px;
    padding: 0 24px;
  }

  > ol {
    > li {
      > a {
        display: block;
        padding: 10px 24px;

        &:hover {
          text-decoration: none;
        }
      }

      .router-link-active {
        background: rgba(67, 185, 127, 0.1);
        border-right:4px solid rgba(67, 185, 127 );
        color:rgba(67, 185, 127) ;
        //&::after {
        //  position: absolute;
        //  right: 0;
        //  width: 5px;
        //  height: auto;
        //  background: rgba(67, 185, 127);
        //}
      }

    }
  }

  @media (max-width: 500px) {
    padding-top: 90px;
    position: fixed;
    top: 0;
    left: 0;
  }
}

.layout {
  display: flex;
  flex-direction: column;
  height: 100vh;

  > .nav {
    flex-shrink: 0;
  }

  > .content {
    flex-grow: 1;
    padding-top: 60px;
    padding-left: 270px;
    @media (max-width: 500px) {
      padding-left: 0;
    }
  }
}

.content {
  display: flex;

  > aside {
    flex-shrink: 0;
  }

  > main {
    flex-grow: 1;
    padding: 16px;
    background: white;
  }
}
</style>