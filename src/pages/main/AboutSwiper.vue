<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import { ref } from "vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

import { Photo } from "@/entities";
import { ArrowLeftIcon, ArrowRightIcon } from "@/shared/icons";

import image1 from "@/shared/assets/images/about/swiper1.jpg";
import image2 from "@/shared/assets/images/about/swiper2.jpg";
import image3 from "@/shared/assets/images/about/swiper3.jpg";

const modules = ref([Navigation, Pagination]);
const prev = ref(null);
const next = ref(null);

const aboutSwiperList = [
  { id: 1, img: image1 },
  { id: 2, img: image2 },
  { id: 3, img: image3 },
  { id: 4, img: image1 },
  { id: 5, img: image2 },
  { id: 6, img: image3 },
];
</script>

<template>
  <div class="about-swiper">
    <div class="navigation">
      <button ref="prev" variant="clear"><ArrowLeftIcon /></button>
      <button ref="next" variant="clear"><ArrowRightIcon /></button>
    </div>
    <Swiper
      :pagination="{
        clickable: true,
      }"
      :slidesPerView="3"
      :spaceBetween="32"
      :centeredSlides="true"
      :loop="true"
      :navigation="{
        prevEl: prev,
        nextEl: next,
      }"
      :modules="modules"
      class="swiper-about"
    >
      <SwiperSlide v-for="item in aboutSwiperList" :key="item.id">
        <Photo :img="item.img" />
      </SwiperSlide>
    </Swiper>
  </div>
</template>

<style lang="scss">
.swiper-about {
  height: 600px;
  display: flex;
  align-items: center;
  .swiper-wrapper {
    align-items: center !important;
    height: fit-content !important;
  }
  .swiper-pagination {
    bottom: 0;
    .swiper-pagination-bullet {
      width: 15px;
      height: 15px;
    }
    .swiper-pagination-bullet-active {
      background: var(--purple-color) !important;
    }
  }
}
</style>
<style lang="scss" scoped>
.about-swiper {
  position: relative;
  .navigation {
    pointer-events: none;
    z-index: 2;
    position: absolute;
    width: 100%;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: auto;
    button {
      pointer-events: all;

      display: flex;
      align-items: center;
      justify-content: center;
      width: 36px;
      height: 36px;
      border-radius: 999px;
      background: var(--yellow-color);
      svg {
        stroke: var(--white-color);
        path {
          fill: var(--white-color);
        }
      }
    }
  }
  .swiper-slide {
    transform: scale(0.8);
    transition: var(--trs-300);
    height: 100% !important;
    .photo {
      height: calc(25vw / 1.1);
      width: 100%;
      transition: var(--trs-300);
    }
  }
  .swiper-slide-active {
    transform: scale(1.2);
    height: 100% !important;
  }
}
</style>
