<template>
  <div>
    <Message />
    <!-- 這裡要怎麼這裡要怎麼樣的type傳給我呢 布林值控制顯示嗎? -->
    <div class="dialog-box">
      <img :src="Avatar" alt="Avatar Img">
      <div class="giftRoll-box">
        <div class="giftRoll">
          <p>您收到了 {{ giftData.quantity }} 張「{{ giftData.title }}」</p>
          <img :src="giftData.image" alt="giftCard">
          <p class="title">{{ giftData.title }}</p>
          <div class="gift-content">
            <div v-if="giftDataShow === false">
              <h6>到期日期</h6>
              <div class="discount-content">
                <h6>優惠內容</h6>
                <img src="../assets/giftcontent.png" alt="giftcontent">
              </div>
            </div>
            <div v-else>
              <h6>{{ giftData.date }}到期</h6>
              <div class="discount-content">
                <h6>優惠內容</h6>
              <div class="content-text">{{ giftData.discountContent }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>
  

<script lang="ts">
import Vue from 'vue';
import SvgAvatar from '../assets/avatar.svg';
import Message from './Message.vue';

export default Vue.extend ({
  components: {
    Message
  },
  data() {
    return {
      Avatar: SvgAvatar
    }
  },
  props: {
    lineGiftRoll: {
      type: String,
      default: '嗨～專屬優惠送給你！會員獨享到店到店滿 200 元就送 noii noii 貼紙！💛'
    },
    title:{
      type: String,
      default: 'Cheers! 茉玉春蘋體驗券'
    },
    quantity:{
      type: Number,
      default: 1
    },
    giftDataShow:{
      type: Boolean,
      default: true
    },
    giftData: {
      type: Object,
      default() {
        return {
          quantity: 1,
          date: '10/5',
          discountContent: '入會即贈限定調酒',
          image: require('../assets/giftcard.png'),
          title: 'Cheers! 茉玉春蘋體驗券'
        };
      }
    }
  }
}); 
  
</script>
  
<style scoped>
.dialog-box{
  display: flex;
  align-items: flex-start;
}
.giftRoll-box{
  display: flex;
  margin: 0px 0px 8px 8px;
}
.giftRoll{
  width: 200px;
  height:356px;
  background-color: white;
  border-radius: 18px;
  word-wrap: break-word;
}
.gift-content{
  font-family: "Noto Sans TC", sans-serif;
}
p{
  font-family: "Noto Sans TC", sans-serif;
  font-weight: 600;
  font-size: 13px;
  line-height:19px;
  color: #606266;
  padding: 0px 15px;
}
h6{
  font-size: 10px;
  font-weight: 500;
  line-height: 16px;
  color: #ACACAC;
  margin: 4px 0px;
  padding: 0px 15px;
}
.gift-content > div > img{
  border-radius: 8px;
}
.title{
  margin-bottom: 0px;
}
.discount-content{
  margin: 10px 0px;
}
.content-text{
  font-weight: 400;
  padding: 0px 15px;
  font-size: 12px;
}
</style>
  