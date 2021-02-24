<template>
  <div class="chat_wrap">
    <nuxt-link :to="'#!'" class="chat_link">
      <img :src="chat" alt="" />
      <span>Чат</span>
    </nuxt-link>
  </div>
</template>
<script>
import chat_icon from "../../assets/img/chat_icn.svg";
export default {
  data: () => ({
    chat: chat_icon
  })
};
</script>
<style lang="scss" scoped>
.chat_link {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-weight: 500;
  font-size: 15px;
  line-height: 18px;
  color: #616D75;
  text-decoration: none;
}
</style>
