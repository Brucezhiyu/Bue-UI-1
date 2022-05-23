<template>
  <div>
    dialog
  </div>
  <h1>示例1</h1>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="x" :closeOnClickOverlay="true" :ok="f1" :cancel="f2">
    <div>提示1</div>
    <div>提示2</div>
  </Dialog>
</template>
<script lang="ts">
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue';
import {ref} from 'vue';
export default {
  components:{
    Dialog,
    Button
  },
  setup(){
    const x=ref(false)
    const f1=()=>{
      return false
    }
    const f2=()=>{}
    const toggle=()=>{
      x.value=!x.value
    }
    return{x,toggle,f1,f2}
  }

}
</script>

<style lang="scss" scoped>

</style>