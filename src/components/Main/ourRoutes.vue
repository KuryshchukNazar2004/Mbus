<template>
  <v-container class="mt-8">
    <v-row
      no-gutters
      class="mb-2 text-center"
      justify="center"
      style="font-weight: 500; font-size: 32px; color: #243949"
    >
      <v-col cols="9" class="pa-0">Наші маршрути</v-col>
    </v-row>
    <v-row
      no-gutters
      class="mb-2 text-center"
      justify="center"
      style="font-weight: 500; font-size: 16px; color: #4c5d6c"
    >
      <v-col cols="9" class="pa-0"
        >Ми виконуємо регулярні автобусні перевезення пасажирві по наступних
        напрямках:</v-col
      >
    </v-row>
    <swiper
      class="d-none d-lg-block pt-5 pb-5"
      :style="{
        '--swiper-navigation-color': '#000000',
      }"
      :options="swiperOption"
    >
      <swiper-slide v-for="i in 9" :key="i">
        <routes-card />
      </swiper-slide>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>
  </v-container>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
import routesCard from "../Routes/routesCard.vue";
export default {
  name: "swiper-example-loop-group",
  title: "Loop mode with multiple slides per group",
  components: {
    Swiper,
    SwiperSlide,
    routesCard,
  },
  data() {
    return {
      indexItem: 0,
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 0,
        slidesPerGroup: 3,
        loop: false,
        loopFillGroupWithBlank: false,
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },
      },
      swiperMobileOption: {
        slidesPerView: 1,
        spaceBetween: 0,
        slidesPerGroup: 1,
        loop: false,
        loopFillGroupWithBlank: false,
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },
      },
      swiperMediumOption: {
        slidesPerView: 2,
        spaceBetween: 0,
        slidesPerGroup: 2,
        loop: false,
        loopFillGroupWithBlank: false,
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },
      },
    };
  },
};
</script>

<style scoped>
.swiper-slide {
  text-align: center;
}
.swiper-button-prev:after,
.swiper-button-next:after {
  font-size: 30px;
}
</style>