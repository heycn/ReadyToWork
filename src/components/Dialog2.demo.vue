<demo>一键打开对话框</demo>
<template>
  <div>
    <Button @click="showDialog">打开对话框</Button>
  </div>
</template>

<script lang="ts">
import {
  Button,
  openDialog
} from '../lib/index';
import {
  ref,
  h
} from 'vue';

export default {
  components: {
    Button
  },
  setup() {
    const showDialog = () => {
      openDialog({
        title: h('strong', {}, '提示'),
        content: '我不服！我就只是个提示的对话框，你爱怎么关就怎么关！',
        ok() {
          console.log('ok');
        },
        cancel() {
          console.log('cancel');
        }
      });
    };
    return {
      showDialog
    };
  }
};
</script>