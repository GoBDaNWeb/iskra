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
.main-swiper {
  .swiper-pagination-bullet {
    width: 15px !important;
    height: 15px !important;
    background: var(--yellow-color) !important;
    opacity: 1;
  }
  .swiper-pagination-bullet-active {
    background: var(--purple-color) !important;
  }
}
</style>
<style lang="scss" scoped>
.main-swiper {
  height: calc(20vw * 1.1);
  position: relative;
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
