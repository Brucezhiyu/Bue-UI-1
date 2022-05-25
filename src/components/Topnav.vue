<template>
  <div class="topnav">
    <router-link to="/" class="logo">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-icon-b"></use>
      </svg>
      Bue UI
    </router-link>
    <ul class="menu">
      <li>
        <router-link to="/doc">文档</router-link>
      </li>

    </ul>
    <span v-if="toggleMenuButtonVisible" class="toggleAside" @click="toggleMenu">
      <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-menu"></use>
          </svg>
    </span>
  </div>
</template>
<script lang="ts">
import {inject, Ref} from 'vue';

export default {
  props:{
    toggleMenuButtonVisible:{
      type:Boolean,
      default:false
    }
  },
  setup() {
    const menuVisible = inject<Ref<boolean>>('menuVisible');
    const toggleMenu = () => {
      menuVisible.value = !menuVisible.value;
    };
    return {toggleMenu};
  }
};
</script>
<style lang="scss" scoped>
.topnav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: white;
  display: flex;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
  color: rgba(2, 39, 61);
  padding: 20px;
  z-index: 20;
  justify-content: center;
  align-items: center;

  > .logo {
    &:hover {
      text-decoration: none;
    }
    max-width: 8em;
    margin-right: auto;
    >.icon{
      width: 30px;
     height: 20px;
    }

  }

  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;

    > li {
      margin: 0 1em;
    }
  }

  > .toggleAside {
    width: 24px;
    height: 24px;
    position: absolute;
    left: 24px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
    >.icon{
      width: 24px;
      height: 24px;
    }

  }

  @media (max-width: 500px) {
    > .menu {
      display: none;
    }
    > .logo {
      margin: 0 auto;
    }
    > .toggleAside {
      display: inline-block;

    }
  }
}
</style>