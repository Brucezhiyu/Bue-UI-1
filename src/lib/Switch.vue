<template>
  <div>
    <button @click="toggle" :class="{checked:checked}"><span></span></button>
  </div>
</template>

<script lang="ts">
import {ref} from 'vue';

export default {
  setup() {
    const checked = ref(false);
    const toggle=()=>{
      checked.value=!checked.value;
    }
    return {checked,toggle};
  }
};
</script>

<style lang="scss" scoped>
button {
  height: 22px;
  width: 44px;
  border: none;
  background: lightgrey;
  border-radius: 11px;
  position: relative;
}

span {
  position: absolute;
  top: 2px;
  left: 2px;
  height: 18px;
  width: 18px;
  border-radius: 9px;
  background: white;
}
button.checked{
  background: dodgerblue;
}
button.checked > span {
  left: calc(100% - 20px);

}
</style>