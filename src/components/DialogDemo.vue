<template>
  <div>
    dialog
  </div>
  <h1>示例1</h1>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="x" :closeOnClickOverlay="true" :ok="f1" :cancel="f2">
    <template v-slot:content>
      <div>提示</div>
      <strong>加粗的提示</strong>
    </template>
    <template v-slot:title>
      <strong>加粗的标题</strong>
    </template>
  </Dialog>
  <h1>示例2</h1>
  <Button @click="showDialog">show</Button>
</template>
<script lang="ts">
import Dialog from '../lib/Dialog.vue';
import Button from '../lib/Button.vue';
import {ref} from 'vue';
import {openDialog} from '../lib/openDialog';

export default {
  components: {
    Dialog,
    Button
  },
  setup() {
    const x = ref(false);
    const f1 = () => {
      return false;
    };
    const f2 = () => {
    };
    const showDialog = () => {
      //一句话打开Dialog
      openDialog({
        title: '标题',
        content: '内容',
        ok() {
          console.log('ok');
        },
        cancel() {
          console.log('cancel');
        }
      });

    };
    const toggle = () => {
      x.value = !x.value;
    };
    return {x, toggle, f1, f2, showDialog};
  }

};
</script>

<style lang="scss" scoped>

</style>