<template>
  <div class="bottom-menu">
    <img :src="SvgKeyboard" alt="keyboard image">
    <div class="menu-text-box">
      <div class="menu-text-style">{{ MenuText }}</div>
      <img :src="SvgTriangle" alt="triangle image" class="triangle">
    </div>
  </div>
</template>

<script lang="ts">
import SvgKeyboard from '../assets/keyboard.svg';
import SvgTriangle from '../assets/triangle.svg';

export default {
  data() {
    return {
      initData: 'hello 你好',
      SvgKeyboard: SvgKeyboard,
      SvgTriangle:SvgTriangle
    }
  },
  props: {
    MenuText: {
      type: String,
      default: '選單',
    }
  }
}
</script>

<style scoped>
.bottom-menu {
  width: 300px;
  height: 44px;
  background-color: white;
  border-radius: 0px 0px 14px 14px;
  display: flex;
  align-items: center;
  color: #606266;
}

.menu-text-box {
  display: flex;
  align-items: center;
  flex: 1;
  justify-content: center;
}

.triangle {
  width: 5.21px;
  height: 4.93px;
}

.bottom-menu>img {
  margin-left: 16px;
}

.menu-text-style {
  font-family: Noto Sans SC;
  font-size: 12.28px;
  font-weight: 400;
  line-height: 15.79px;
}
</style>
