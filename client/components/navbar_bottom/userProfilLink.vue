<template>
  <div style="height:100%;">
    <nuxt-link class="user_link" to="#!">
      <div class="avatar">
        <img :src="img" alt="" />
      </div>
      <div class="user_title">
        <div class="user_name">
          {{ name }}
        </div>
        <div class="user_price">{{ price }} сум</div>
      </div>
    </nuxt-link>
  </div>
</template>
<script>
export default {
  props: {
    img: {
      type: String,
      default: "../../assets/img/Avatar.svg"
    },
    name: {
      type: String,
      default: "user" + Date.now()
    },
    price: {
      type: Number,
      default: 0
    }
  }
};
</script>
<style lang="scss" scoped>
.user_link {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
  .avatar{
    margin-right: 7px;
  }
  .user_name {
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 18px;
    color: #616d75;
    margin-bottom: 5px;
  }
  .user_price {
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 17px;
    color: #616d75;
  }
}
</style>
