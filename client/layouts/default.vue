<template>
  <v-app>
    <nav-top />
    <nav-bottom @activeSidebar="active_sidebar" />
    <v-main>
      <div class="sidebar_xl" :class="{ active: active }">
        <sidebar-xl :sidebar="sidebar" />
      </div>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
import navTop from "../components/navbarTop.vue";
import navBottom from "../components/navbarBottom.vue";
import sidebarXl from "../components/sidebar/sidebar_xl.vue";
import sidebar from "../static/sidebar.js";
export default {
  data() {
    return {
      sidebar,
      active: false
    };
  },
  components: {
    navTop,
    navBottom,
    sidebarXl
  },
  methods: {
    active_sidebar(active) {
      this.active = active;
    }
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600;700;800&display=swap");
* {
  font-family: "Open Sans", sans-serif !important;
}
.v-main {
  padding-top: 20px !important;
  position: relative;
}
// .overlay_sidebar {
//   position: fixed;
//   top: 0;
//   left: 0;
//   width: 100%;
//   height: 100%;
//   backdrop-filter: blur(5px);
//   z-index: 2;
//   background: rgba(42, 42, 42, 0.459);
//   transition-duration: 0.5s;
//   transition-delay: opacity 1s ease-out;
//   opacity: 0;
//   display: none;
//   &.active {
//     opacity: 1;
//     display: block;
//   }
// }
.sidebar_xl {
  position: absolute;
  top: -20px;
  left: 50px;
  z-index: 3;
  transform: translateY(-1000px);
  transition: 1s;
  &.active {
    transform: translateY(0px);
  }
}
</style>
