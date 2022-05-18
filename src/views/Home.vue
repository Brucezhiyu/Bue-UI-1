<template>
<div>
  <div class="topnav">
    <div class="logo">LOGO</div>
    <ul class="menu">
      <li>菜单1</li>
      <li>菜单2</li>
    </ul>
  </div>
  <div class="banner">
    <h1>guluUI</h1>
    <h2>一个哇塞的 UI 框架</h2>
    <p class="actions">
      <a>Github</a>
      <a>开始</a>
    </p>
  </div>
</div>
</template>

<script lang="ts">

</script>

<style lang="scss" scoped>
.topnav {
  background: white;
  display: flex;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.25);
  padding: 20px;
  > .logo {
    max-width: 6em;
    margin-right: auto;
  }
  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;
    > li {
      margin: 0 1em;
    }
  }
}
</style>