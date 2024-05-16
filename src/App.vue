<template>
  <div id="app">
    <div v-if="platform === 'Line'" class="line-preview">
      <div class="background-color">
        <Message v-if="type === 'message'" :lineMessage='initMessage' /> 
        <GiftRoll v-if="type === 'giftRoll'" :lineGiftRoll='initGiftRoll' /> 
      </div>
      <BottomMenu></BottomMenu>
    </div>

  </div>
</template>

<script lang="ts">
import Message from './components/Message.vue';
import BottomMenu from './components/BottomMenu.vue';
import GiftRoll from './components/GiftRoll.vue';

export default {
  components: {
    BottomMenu,
    Message,
    GiftRoll
  },
  data() {
    return {
      initMessage: 'hello 你好',
      initGiftRoll: 'jjj'
    }
  },
  props: {
    platform: {
      type: String,
      default: 'Line'
    },
    type:{
      type:String,
      default: 'giftRoll'
    }
  }
}

</script>

<style scoped>
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
  padding: 35px 10px 10px;
  overflow: auto;
  box-sizing: border-box;
}
.background-color::-webkit-scrollbar-thumb  {
  background: #D9D9D9;
  border-radius: 2px;
  opacity: 0.4; 
}

.background-color::-webkit-scrollbar {
  width: 4px;
  height: 8px;
  margin: 20px;
}

</style>
