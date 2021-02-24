<template>
  <div class="sidebar_elru" :class="classes"> 
    <div class="row_sidebar">
      <div class="item_col" v-for="n in sidebar" :key="n._id">
        <nuxt-link class="sidebar_link" active-class="sidebar_link_active" :to="n.href">{{ n.item }}</nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    classes:{
      type:String,
    },
    sidebar:{
      type:Array,
      required:true
    }
  }
};
</script>
<style lang="scss" scoped>
.sidebar_elru {
  max-width: 860px;
  padding: 30px;
  background: #fff;
  .row_sidebar {
    display: flex;
    flex-wrap: wrap;
    margin-right: -20px;
    margin-left: -20px;
    .item_col {
      width: calc(100% / 4);
      padding: 20px;
      .sidebar_link {
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #616d75;
        text-decoration: none;
        &_active{
          color: #01BEDE;
          text-decoration-line: underline;
        }
      }
    }
  }
}
</style>
