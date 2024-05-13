<template>
  <div id="app">
    <preview
      platform = "'IOS' || 'ANDROID' || 'LINE' || 'WHATSAPP' || 'MESSENGER'"
      messages[] = "{
        type,
        content{...},
      }"
    />
    <div v-if="platform === 'LINE'" class="linePreview">
      <div class="bg">
        <Text :propData='initData'/>
      </div>
      <div class="buttonMenu">
        <img :src="svg" alt="keyboard image">
        <div class="MenuTextBox">
          <div class="MenuTextStyle">{{ MenuText }}</div>
          <img :src="triangle" alt="triangle image" class="triangle">
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import Text from './components/Text.vue'
import svg from './assets/keyboard.svg';
import triangle from './assets/triangle.svg'

export default {
  data(){
    return {
      platform: 'LINE',
      initData: 'hello 你好',
      svg: svg,
      triangle: triangle
    }
  },
  components:{
    Text
  },
  props: {
    MenuText: {
      type: String,
      default: '選單',
    }
  }
}

</script>

<style>
.linePreview{
  border: 0.88px solid #E5E7EB;
  box-shadow: 0px 0px 10px 0px #0000001A;
  width: 300px;
  height:563px;
  border-radius:14px 14px 14px 14px;
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
  display: flex;
  align-items: center;
  color: #606266;
}
.MenuTextBox{
  display: flex;
  align-items: center;
  flex: 1;
  justify-content: center;
}
.triangle{
  width:5.21px;
  height:4.93px;
}
.buttonMenu > img{
  margin-left: 16px;
}
.MenuTextStyle{
  font-family: Noto Sans SC;
  font-size: 12.28px;
  font-weight: 400;
  line-height: 15.79px;
}


</style>
