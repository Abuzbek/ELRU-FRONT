<template>
  <v-btn tile color="#01BEDE" class="btn_menu_navbar" @click="closeMenu">
    <!-- <v-icon left v-if="!close">
        mdi-menu
      </v-icon>
      <v-icon left v-else-if="close">
        mdi-close
      </v-icon> -->
    <div class="btn_icon">
      <span :class="{ 'toggle': close }"></span>
      <span :class="{ 'close': close }"></span>
      <span :class="{ 'toggle': close }"></span>
    </div>
    Категории
  </v-btn>
</template>
<script>
export default {
  data: () => ({
    close: false
  }),
  methods: {
    closeMenu() {
      this.close = !this.close;
      this.$emit('clickedSidebar', {close:this.close})
      console.log(this.close);
    }
  }
};
</script>
<style lang="scss" scoped>
.btn_menu_navbar {
  padding: 0px !important;
  padding-left: 30px !important;
  padding-right: 30px !important;
  color: white !important;
  height: 100% !important;
  font-weight: bold;
  box-shadow: none !important;
  .btn_icon {
    position: relative;
    width: 20px;
    height: 15px;
    overflow:hidden;
    span {
      position: absolute;
      display: block;
      width: 15px;
      height: 2px;
      background: white;
      transition-duration: 0.5s !important;
      &:first-child {
        top: 0px;
        
        &.toggle {
          transform: rotate(45deg);
          width: 20px;
          top: 6px;
          transition-delay: 0.5s;
        }
      }
      &:nth-child(2) {
        top: calc(2px + 3px);
        &.close {
          transform: translateX(-70px);
          // transition-delay: 1s;
        }
      }
      &:nth-child(3) {
        top: calc(2px + 8px);
        &.toggle {
          transform: rotate(-45deg);
          width: 20px;
          top: 6px;
        transition-delay: 0.5s;

        }
      }
    }
  }
}
</style>
