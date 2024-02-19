<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import { ref } from "vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

import { Photo } from "@/entities";
import { ArrowLeftIcon, ArrowRightIcon } from "@/shared/icons";

const modules = ref([Navigation, Pagination]);
const prev = ref(null);
const next = ref(null);
const pagination = ref(null);

defineProps(["swiperClass"]);
</script>

<template>
  <div class="main-swiper" :class="swiperClass">
    <div class="navigation">
      <button ref="prev" variant="clear"><ArrowLeftIcon /></button>
      <button ref="next" variant="clear"><ArrowRightIcon /></button>
    </div>
    <Swiper
      :pagination="{
        el: pagination,
        clickable: true,
      }"
      :slidesPerView="1"
      :spaceBetween="10"
      :centeredSlides="true"
      :loop="true"
      :navigation="{
        prevEl: prev,
        nextEl: next,
      }"
      :modules="modules"
      class="swiper-house"
    >
      <slot></slot>
    </Swiper>
    <div ref="pagination" class="pagination"></div>
  </div>
</template>

<style lang="scss">
@import "@/shared/styles/vars";

.main-swiper {
  .swiper-pagination-bullet {
    width: 15px;
    height: 15px;
    background: var(--yellow-color);
    opacity: 1;
    @media (max-width: $tab) {
      width: 10px !important;
      height: 10px !important;
    }
  }
  .swiper-pagination-bullet-active {
    background: var(--purple-color) !important;
  }
}
</style>
<style lang="scss" scoped>
@import "@/shared/styles/vars";

.main-swiper {
  max-height: 434px;
  height: calc(20vw * 1.52);
  position: relative;
  @media (max-width: $tab) {
    height: calc(20vw * 2.7);
  }
  .swiper {
    height: 100%;
  }
  .navigation {
    pointer-events: none;
    z-index: 2;
    position: absolute;
    width: 100%;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    padding-right: 15px;
    padding-left: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: auto;
    @media (max-width: $tab) {
      display: none;
    }
    button {
      pointer-events: all;

      display: flex;
      align-items: center;
      justify-content: center;
      width: 36px;
      height: 36px;
      border-radius: 999px;
      background: var(--white-color);
      svg {
        stroke: var(--purple-color);
      }
    }
  }
  .pagination {
    display: flex;
    justify-content: center;
    margin-top: 25px;
  }
}
</style>
