<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import { ref } from "vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

import { ArrowLeftIcon, ArrowRightIcon } from "@/shared/icons";

const modules = ref([Navigation, Pagination]);
const prev = ref(null);
const next = ref(null);
const pagination = ref(null);

defineProps(["pagColor"]);
</script>

<template>
  <div class="triple-swiper" :class="pagColor">
    <div class="navigation">
      <button ref="prev" variant="clear"><ArrowLeftIcon /></button>
      <button ref="next" variant="clear"><ArrowRightIcon /></button>
    </div>
    <Swiper
      :pagination="{
        el: pagination,
        clickable: true,
      }"
      :slidesPerView="3.1"
      :spaceBetween="30"
      :navigation="{
        prevEl: prev,
        nextEl: next,
      }"
      :breakpoints="{
        0: { slidesPerView: 1.1, spaceBetween: 15 },
        767: { slidesPerView: 2.1 },
        1024: { slidesPerView: 3.1, spaceBetween: 30 },
      }"
      :modules="modules"
      class="swiper-triple"
    >
      <slot></slot>
    </Swiper>
    <div ref="pagination" class="pagination"></div>
  </div>
</template>

<style lang="scss">
.triple-swiper.purple {
  .swiper-pagination-bullet {
    width: 15px;
    height: 15px;
    background: var(--white-color);
    opacity: 1;
  }
  .swiper-pagination-bullet-active {
    background: var(--purple-color);
  }
}
.triple-swiper.yellow {
  .swiper-pagination-bullet {
    width: 15px;
    height: 15px;
    background: var(--white-color);
    opacity: 1;
  }
  .swiper-pagination-bullet-active {
    background: var(--yellow-color);
  }
}
.triple-swiper {
  .swiper-triple {
    overflow: visible;
  }
  .pagination {
    display: flex;
    justify-content: center;
    margin-top: 45px;
  }
}
</style>
<style lang="scss" scoped>
@import "@/shared/styles/vars";

.triple-swiper {
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
    margin: auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    @media (max-width: $tab) {
      display: none;
    }
    button {
      pointer-events: all;
      position: absolute;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 36px;
      height: 36px;
      border-radius: 999px;
      background: var(--white-color);
      box-shadow: var(--shadow);
      svg {
        stroke: var(--purple-color);
      }
      &:first-child {
        left: -45px;
      }
      &:last-child {
        right: -45px;
      }
    }
  }
  .swiper-slide {
    p {
      margin-top: 15px;
      color: var(--white-color);
      font-weight: 400;
      font-size: 20px;
      line-height: 28px;
    }
  }
}
</style>
