<template>
  <v-app-bar app color="#F3F6F9" class="navbar_bottom_elru" height="70px">
    <div class="btn_navbar_menu">
      <btn-nav @clickedSidebar="activeSidebar"/>
    </div>
    <div class="search_navbar">
      <search-nav />
    </div>
    <div class="navbar_bottom_items">
      <div class="chat_nav">
        <chat-nav />
      </div>
      <div class="save_nav">
        <save-nav />
      </div>
      <div class="basket_nav">
        <basket-nav :count="10" />
      </div>
    </div>
    <div class="user_profil">
      <user-profile :img="avatar" name="AbuzCoder" :price="123000000" />
    </div>
  </v-app-bar>
</template>
<script>
import btnNav from "./navbar_bottom/navbarMenuLayout.vue";
import searchNav from "./navbar_bottom/navbarSearchInput.vue";
import chatNav from "./navbar_bottom/navbarChatLink.vue";
import saveNav from "./navbar_bottom/navbarSaveLink.vue";
import basketNav from "./navbar_bottom/navbarBasketLink.vue";
import userProfile from "./navbar_bottom/userProfilLink.vue";
import avatar from "../assets/img/Avatar.svg";
export default {
  data: () => ({
    avatar
  }),
  components: {
    btnNav,
    searchNav,
    chatNav,
    saveNav,
    basketNav,
    userProfile
  },
  methods:{
    activeSidebar(active){
      console.log(active);
      this.$emit('activeSidebar', active.close)
    }
  }
};
</script>
<style lang="scss">
.navbar_bottom_elru {
  box-shadow: none !important;
  position: relative !important;
  flex: none !important;
  padding-left: calc(50px - 16px);
  padding-right: calc(50px - 16px);
  z-index: 5 !important;
  .v-toolbar__content {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .btn_navbar_menu {
    display: flex;
    justify-content: center;
    height: 100%;
  }
  .search_navbar {
    height: 100%;
  }
  .user_profil{
      height: 100%;
  }
  .navbar_bottom_items {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    .chat_nav,
    .save_nav,
    .basket_nav {
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      padding-left: calc(45px / 2);
      padding-right: calc(45px / 2);
    }
  }
}
</style>
