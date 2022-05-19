<template>
  <div>
    <button class="gulu-switch" @click="toggle" :class="{'gulu-checked':value}"><span></span></button>
  </div>
</template>

<script lang="ts">

export default {
  props: {
    value: Boolean
  },
  setup(props, context) {
    const toggle = () => {
      context.emit('update:value', !props.value);
    };
    return {toggle};
  }
};
</script>

<style lang="scss" scoped>
.gulu-switch{
  z-index: 1;
  height: 22px;
  width: 44px;
  border: none;
  background: lightgrey;
  border-radius: 11px;
  position: relative;
  > span {
    position: absolute;
    top: 2px;
    left: 2px;
    height: 18px;
    width: 18px;
    border-radius: 9px;
    background: white;
    transition: left 250ms;
  }
  &.gulu-checked {
    background: dodgerblue;
  }
  &.gulu-checked > span {
    left: calc(100% - 20px);

  }
  &:focus {
    outline: none;
  }

}
</style>