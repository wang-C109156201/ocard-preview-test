<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container">
    <div class="bg">
      <div>{{ propData }}</div>
    </div>
    <div class="buttonMenu">
      <img :src="svg" alt="keyboard image">
    </div>
  </div>
</template>

<script lang="ts">
import svg from "../src/assets/keyboard.svg";
export default {
  props: {
    propData: {
      type: String,
      default: '我是默认值'
    }
  },
  data() {
    return {
      svg: svg
    };
  }
}
</script>

<style scope>
.container{
  border: 0.88px solid #E5E7EB;
}
.bg {
  width: 300px;
  height: 519px;
  background-color: #8DABD8;
  border-radius:14px 14px 0px 0px;
}
.buttonMenu{
  width: 300px;
  height: 44px;
  background-color: white;
  border-radius:0px 0px 14px 14px;
}
</style>