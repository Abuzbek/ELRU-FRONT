<template>
  <section>
    <header class="header_carousel">
      <v-container fluid class="px-8">
        <v-row>
          <v-col cols="12" lg="8">
            <Carausel :homecarousel="jsoncar" />
          </v-col>
          <v-col cols="12" lg="4">
            <div class="edvest">
              <Edvest
                class="edvest_in"
                v-for="n in edvestJson"
                :key="n._id"
                v-bind="n"
              />
            </div>
          </v-col>
        </v-row>
      </v-container>
    </header>
    <v-container fluid class="px_7_5">
      <Sliders title="Рекомендованное" :cards="json" />
    </v-container>
  </section>
</template>
<script>
import Carausel from "../components/partials/indexCarousel.vue";
import Sliders from "../components/sections/Sliders.vue";
import Edvest from "../components/partials/indexEdvest.vue";
import SwiperCore, { Navigation } from "swiper";
SwiperCore.use([Navigation]);
import json from "../static/index.js";
import jsoncar from "../static/carousel.js";
import edvestJson from "../static/edvest.js";
export default {
  components: {  Carausel, Edvest, Sliders },
  data: () => ({
    json: json,
    jsoncar,
    edvestJson,
  })
};
</script>
<style lang="scss" scoped>
.px_7_5 {
  padding-left: 8px !important;
  padding-right: 8px !important;
}
.header_carousel {
  padding-bottom: 25px;
  .edvest {
    display: flex;
    flex-direction: column;
    &_in:first-child {
      padding-bottom: 15px;
    }
    &_in:nth-child(2) {
      padding-top: 15px;
    }
  }
}
</style>
<style lang="scss" scoped> 

</style>
