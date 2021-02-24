<template>
  <li class="item_navbar">
    <nuxt-link class="item_link" :to="href">{{ item }}</nuxt-link>
  </li>
</template>
<script>
export default {
  props: {
    item: {
      type: String,
      required: true
    },
    href: {
      type: String,
      required: true
    },
    _id: {
      type: String,
      required: true
    }
  }
};
</script>
<style lang="scss" scoped>
.item_navbar {
  padding-left: 20px;
  padding-right: 20px;
  list-style: none;
  display: inline-block;
  .item_link {
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 17px;
    color: #616d75;
    text-decoration: none;
  }
}
</style>
