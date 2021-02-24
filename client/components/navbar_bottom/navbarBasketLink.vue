<template>
  <div class="chat_wrap">
    <nuxt-link :to="'#!'" class="chat_link">
      <span class="count" v-if="count > 9">{{count}}</span>
      <span class="count left" v-if="count === 0">{{0}}</span>
      <span class="count right" v-if="count < 10 && count > 0">{{0}}</span>
      <img :src="chat" alt="" />
      <span>Чат</span>
    </nuxt-link>
  </div>
</template>
<script>
import chat_icon from "../../assets/img/basket_icn.svg";
export default {
  data: () => ({
    chat: chat_icon
  }),
  props:{
    count:{
      type:Number
    }
  }
};
</script>
<style lang="scss" scoped>
.chat_link {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  position: relative;
  font-weight: 500;
  font-size: 15px;
  line-height: 18px;
  color: #616D75;
  text-decoration: none;
  .count{
    font-style: normal;
    position: absolute;
    font-weight: bold;
    font-size: 16px;
    line-height: 19px;
    color: #01BEDE;
    top: -6px;
    left: 11px;
    &.left,
    &.right{
      left:16px !important;
    }
  }
}
</style>
