<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import { ref } from "vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

import { Photo } from "@/entities";
import { ArrowLeftIcon, ArrowRightIcon } from "@/shared/icons";

import img1 from "@/shared/assets/images/rest/swiper1.jpg";
import img2 from "@/shared/assets/images/rest/swiper2.jpg";
import img3 from "@/shared/assets/images/rest/swiper3.jpg";

const modules = ref([Navigation, Pagination]);
const prev = ref(null);
const next = ref(null);
const pagination = ref(null);

const restList = [
  {
    id: 1,
    img: img1,
    text: "Каждое утро начинается с гимнастики, ребенок будет здоровым и активным",
  },
  {
    id: 2,
    img: img2,
    text: "Занимаемся спортом: играем в футбол, теннис, плаваем в бассейне",
  },
  {
    id: 3,
    img: img3,
    text: "Множество интересных кружков и направлений творческого развития",
  },
  {
    id: 4,
    img: img1,
    text: "Каждое утро начинается с гимнастики, ребенок будет здоровым и активным",
  },
  {
    id: 5,
    img: img2,
    text: "Занимаемся спортом: играем в футбол, теннис, плаваем в бассейне",
  },
  {
    id: 6,
    img: img3,
    text: "Каждое утро начинается с гимнастики, ребенок будет здоровым и активным",
  },
];
</script>

<template>
  <div class="rest-swiper">
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
      :modules="modules"
      :breakpoints="{
        0: { slidesPerView: 1 },
        767: { slidesPerView: 2.1 },
        1024: { slidesPerView: 3.1 },
      }"
      class="swiper-rest"
    >
      <SwiperSlide v-for="item in restList" :key="item.id">
        <Photo :img="item.img" />
        <p>{{ item.text }}</p>
      </SwiperSlide>
    </Swiper>
    <div ref="pagination" class="pagination"></div>
  </div>
</template>

<style lang="scss">
.rest-swiper {
  .swiper-rest {
    overflow: visible;
  }
  .pagination {
    display: flex;
    justify-content: center;
    margin-top: 45px;
  }
  .swiper-pagination-bullet {
    width: 15px !important;
    height: 15px !important;
    background: var(--white-color) !important;
    opacity: 1;
  }
  .swiper-pagination-bullet-active {
    background: var(--yellow-color) !important;
  }
}
</style>
<style lang="scss" scoped>
@import "@/shared/styles/vars";

.rest-swiper {
  position: relative;
  .navigation {
    pointer-events: none;
    z-index: 2;
    position: absolute;
    width: 100%;
    top: 127px;
    left: 0;
    right: 0;
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
      @media (max-width: $tab) {
        display: none;
      }
    }
  }
}
</style>
