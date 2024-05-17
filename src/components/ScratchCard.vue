<template>
  <div class="dialog-box">
    <img :src="Avatar" alt="Avatar Img">
    <div class="scratch-card-box">
      <div class="card-text">
        <p class="title">您收到了一張{{ lineMessage }}</p>
        <p>趕緊點按下方按鈕查看</p>
        <div class="line"></div>
        <div class="line-box">
          <div class="line-two"></div>
        </div>
        
      </div>
    </div>
  </div>
</template>
  
  <script lang="ts">
  import SvgAvatar from '../assets/avatar.svg';
  export default {
    data() {
      return {
        Avatar: SvgAvatar
      }
    },
    props: {
      lineMessage: {
        type: String,
        default: '巴拉巴拉'
      }
    }
  }
  </script>
  
<style scoped>
.dialog-box{
  display: flex;
  align-items: flex-start;
}
.scratch-card-box{
  box-sizing: border-box;
  display: flex;
  margin: 0px 0px 8px 8px;
}
.card-text{
  width: 211px;
  height: auto;
  background-color: white;
  border-radius: 8px;
  word-wrap: break-word;
  padding: 5px 0px;
  display: flex;
  flex-direction: column;
}
p{
  font-family: "Noto Sans TC", sans-serif;
  font-size: 10px;
  line-height:14px;
  color: #646363;
  margin-bottom: 0px;
  padding: 0px 15px;
}
.title{
  font-size: 12px;
  font-weight: 700;
  line-height:15px;
  color: #606266;
}
.line{
  width: 100%;
  height: 1px;
  background: var(--secondary_gray_02, #E5E7EB);
  margin-top: 10px;
}
.line-two{
  width: 64px;
  height: 4px;
  border-radius: 2px;
  background: var(--secondary_gray_02, #E5E7EB);
}
.line-box{
  flex:1;
  align-content: center;
  margin: 20px auto;
}
</style>