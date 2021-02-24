<template>
  <div class="search">
    <v-text-field
      v-model="message"
      solo
      class="search_input"
      placeholder="Введите книгу, автора..."
      height="42px"
      clearable
      
    ></v-text-field>
    <v-btn color="#01BEDE" height="45px" class="btn_search">
      <img :src="search_icon" alt="" />
    </v-btn>
  </div>
</template>
<script>
import search_icon from "../../assets/img/search_icon.svg";
export default {
  data() {
    return {
      message: "",
      search_icon: search_icon
    };
  }
};
</script>
<style lang="scss">
.search {
  display: flex;
  align-items: center;
  height: 100%;
  .btn_search {
    border-bottom-left-radius: 0px !important;
    border-top-left-radius: 0px !important;
    box-shadow: none !important;
  }
  .search_input {
    .v-input__control {
      min-height: 45px !important;
    }
    .v-input__slot {
      margin-bottom: 0px !important;
      border-bottom-right-radius: 0px !important;
      border-top-right-radius: 0px !important;
      box-shadow: none !important;
      width:calc(600px - 55px);
      #input-31::placeholder{
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #616D75;
      }
    }
    .v-text-field__details {
      display: none;
    }
  }
}
</style>
