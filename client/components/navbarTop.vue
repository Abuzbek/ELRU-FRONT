<template>
  <v-app-bar app color="#fff" absolute class="navbar_top_elru" height="50px">
    <div class="logo">
      <img :src="logo" alt="" />
    </div>
    <div class="items">
      <navbar-top-items v-for="(n, i) in itemNavTop" :key="i" v-bind="n" />
    </div>
    <div class="phone">
      <navbar-top-phone phone='+998 99 314 42 63' />
    </div>
  </v-app-bar>
</template>
<script>
import logo from "../assets/img/logo.png";
import navbarTopItems from "./navbarTopItems";
import navbarTopPhone from "./navTopPhone";

export default {
  data: () => ({
    logo,
    itemNavTop: [
      {
        item: "Акции и скидки",
        _id: "sacj893wji9e0",
        href: "#!"
      },
      {
        item: "Топ - книги",
        _id: "sacj893wji9e0",
        href: "#!"
      },
      {
        item: "Новости",
        _id: "sacj893wji9e0",
        href: "#!"
      },
      {
        item: "Оплата",
        _id: "sacj893wji9e0",
        href: "#!"
      },
      {
        item: "Обратная связь",
        _id: "sacj893wji9e0",
        href: "#!"
      }
    ]
  }),
  components:{
    navbarTopPhone,
    navbarTopItems
  }
};
</script>
<style lang="scss" scoped>
.navbar_top_elru {
  box-shadow: none !important;
  .logo {
    padding-left: calc(50px - 16px);
    padding-top: calc(10px - 4px);
    padding-bottom: calc(10px - 4px);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .items {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
}
</style>
