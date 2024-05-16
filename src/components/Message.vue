<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="dialog-box">
    <img :src="Avatar" alt="Avatar Img">
    <div class="message-box">
      <img :src="Vector" class="vector-size" alt="Vector Img">
      <div class="message">
        <div>{{ lineMessage }}</div>
      </div>
    </div>

  </div>


</template>

<script lang="ts">
import SvgAvatar from '../assets/avatar.svg';
import SvgVector from '../assets/vector.svg';
export default {
  data() {
    return {
      Avatar: SvgAvatar,
      Vector: SvgVector
    }
  },
  props: {
    lineMessage: {
      type: String,
      default: '嗨～專屬優惠送給你！會員獨享到店到店滿 200 元就送 noii noii 貼紙！💛'
    }
  }
}
</script>

<style scoped>
.dialog-box{
  display: flex;
  align-items: flex-start;
}
.message-box{
  display: flex;
  margin: 0px 0px 8px 8px;
}
.message{
  background-color: white;
  min-width: 48px;
  min-height: 30px;
  border-radius: 18px;
  margin-left: -8px;
  max-width: 210px;
  word-wrap: break-word;
  padding: 0px 10px;
  font-family: "Noto Sans TC", sans-serif;
  font-weight: 400;
  font-size: 12px;
  line-height:16px;
  color: #606266;
  align-content: center;
}
.vector-size{
  width:8.27px;
  height:10.09px;
}
</style>