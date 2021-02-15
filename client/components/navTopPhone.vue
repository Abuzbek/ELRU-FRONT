<template>
  <li class="phone_navbar">
    <img :src="phones" alt="phone" />
    <a :href="'tel:'+phone">{{ phone }}</a>
  </li>
</template>
<script>
import phones from "../assets/img/phone.svg";
export default {
  data:()=>({phones}),
  props: {
    phone: {
      type: String,
      required: true
    }
  }
};
</script>
<style lang="scss" scoped>
.phone_navbar {
  display: flex;
  justify-content: center;
  align-items: center;
  a {
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 17px;
    color: #616d75;
    text-decoration: none;
    margin-left: 7px;
  }
}
</style>
