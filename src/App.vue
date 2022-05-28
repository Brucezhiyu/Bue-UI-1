<template>
  <router-view/>
  <img src="./assets/man.png" class="rightBox">
</template>

<script lang="ts">

import {provide, ref} from 'vue';
import {router} from './router';

export default {
  name: 'App',
  setup() {
    const width = document.documentElement.clientWidth;
    const menuVisible = ref(width <= 500 ? false : true);
    provide('menuVisible', menuVisible);
    router.afterEach(()=>{
      if (width<=500){
        menuVisible.value=false
      }
    })
  }

};
</script>
<style lang="scss">
.rightBox{

  @media (min-width: 1200px) {

    width: 350px;
    height: 410px;
    right: 200px;
    bottom: 150px;
    position: fixed;
    background-size: 100%;
    background-image: url("/src/assets/man.png");
  }
}
</style>