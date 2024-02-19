<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import { ref } from "vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import { Badge } from "@/shared/ui";

import { Photo } from "@/entities";
import { ArrowLeftIcon, ArrowRightIcon } from "@/shared/icons";

const modules = ref([Navigation, Pagination]);
const prev = ref(null);
const next = ref(null);
const pagination = ref(null);

const props = defineProps(["title", "badges", "text"]);
</script>

<template>
  <div class="default-swiper">
    <div class="content">
      <h5 v-if="title">{{ title }}</h5>
      <p v-if="text">{{ text }}</p>
      <div class="badges" v-if="badges">
        <Badge variable="primary" v-for="badge in badges" :key="badge">
          {{ badge }}
        </Badge>
      </div>
    </div>

    <div class="swiper-wrapper">
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
        class="swiper-default"
      >
        <slot></slot>
      </Swiper>
    </div>
    <div ref="pagination" class="pagination"></div>
  </div>
</template>

<style lang="scss">
.default-swiper {
  .swiper-default {
    padding-left: 10px;
    padding-bottom: 10px;
    .swiper-slide {
      .photo {
        height: 100%;
      }
    }
  }
  .pagination {
    display: flex;
    justify-content: center;
    margin-top: 25px;
  }
  .swiper-pagination-bullet {
    width: 15px !important;
    height: 15px !important;
    background: var(--gray-color) !important;
    opacity: 1;
  }
  .swiper-pagination-bullet-active {
    background: var(--purple-color) !important;
  }
}
</style>
<style lang="scss" scoped>
@import "@/shared/styles/vars";

.default-swiper {
  display: flex;
  flex-direction: column;
  height: 100%;
  justify-content: space-between;
  .content {
    flex: 1 1;
  }
  .swiper-wrapper {
    max-height: 370px;
    height: 100%;
    @media (max-width: $tab) {
      max-height: 100%;
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
  }
  h5 {
    font-weight: 700;
    font-size: 32px;
    line-height: 35px;
    @media (max-width: $tab) {
      font-size: 28px;
      line-height: 33px;
    }
  }
  p {
    margin-top: 18px;
    margin-bottom: 45px;
    font-weight: 400;
    font-size: 20px;
    line-height: 28px;
    max-width: 605px;
    @media (max-width: $tab) {
      font-size: 18px;
      line-height: 25px;
    }
  }
  .badges {
    display: flex;
    gap: 7px;
    margin-bottom: 22px;
    margin-top: 20px;
    .badge {
      font-weight: 400;
      font-size: 20px;
      line-height: 30px;
      height: 45px;
      padding: 0 30px;
      display: flex;
      align-items: center;
    }
  }
}
</style>
