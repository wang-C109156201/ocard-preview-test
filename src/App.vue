<template>
  <div id="app">
    <div v-if="platform === 'Line'" class="line-preview">
      <div class="background-color">
        <Message :propData='initData' />
      </div>
      <BottomMenu></BottomMenu>
    </div>

  </div>
</template>

<script>
import Message from './components/Message.vue';
import BottomMenu from '@/components/BottomMenu.vue';

export default {
  components: {
    BottomMenu,
    Message
  },
  data() {
    return {
      initData: 'hello 你好'
    }
  },
  props: {
    platform: {
      type: String,
      default: 'Line'
    }
  }
}

</script>

<style>
.line-preview {
  border: 0.88px solid #E5E7EB;
  box-shadow: 0px 0px 10px 0px #0000001A;
  width: 300px;
  height: 563px;
  border-radius: 14px 14px 14px 14px;
}

.background-color {
  width: 300px;
  height: 519px;
  background-color: #8DABD8;
  border-radius: 14px 14px 0px 0px;
  padding: 12px;
  overflow: auto;
  box-sizing: border-box;
}

</style>
