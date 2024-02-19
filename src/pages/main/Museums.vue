<script setup>
import { SwiperSlide } from "swiper/vue";
import { Badge } from "@/shared/ui";
import { DefaultSwiper, Photo } from "@/entities";

import img1 from "@/shared/assets/images/museums/1.jpg";
import img2 from "@/shared/assets/images/museums/2.jpg";
const museumsList1 = [
  { id: 1, img: img1 },
  { id: 2, img: img1 },
  { id: 3, img: img1 },
];
const museumsList2 = [
  { id: 1, img: img2 },
  { id: 2, img: img2 },
  { id: 3, img: img2 },
];
</script>

<template>
  <div class="museums">
    <div class="container">
      <div class="museums-inner">
        <div class="top">
          <h3>Музеи</h3>
        </div>
        <div class="bottom">
          <div class="museums-item">
            <DefaultSwiper
              :title="'Музей воинской славы'"
              :text="'В музее продемонстрированы различные виды оружия, обмундирования и предметов быта периода Великой Отечественной войны'"
            >
              <SwiperSlide v-for="img in museumsList1" :key="img.id">
                <Photo :img="img.img" />
              </SwiperSlide>
            </DefaultSwiper>
          </div>
          <div class="museums-item">
            <DefaultSwiper
              :title="'Музей «Русская изба»'"
              :text="'Является хранилищем предметов домашнего обихода, прикладного искусства и элементов русского народного костюма'"
            >
              <SwiperSlide v-for="img in museumsList2" :key="img.id">
                <Photo :img="img.img" />
              </SwiperSlide>
            </DefaultSwiper>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.museums {
  position: relative;
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-education.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
  }
  .museums-inner {
    padding-top: 140px;
    padding-bottom: 100px;
    @media (max-width: $tab) {
      padding-top: 0;
    }
    .top {
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        @media (max-width: $tab) {
          font-size: 40px;
          line-height: 44px;
          margin-bottom: 40px;
        }
      }
    }
    .bottom {
      display: flex;
      align-items: center;
      gap: 30px;
      margin-top: 48px;
      @media (max-width: $tab) {
        flex-direction: column;
        gap: 76px;
      }

      .museums-item {
        width: 50%;
        @media (max-width: $tab) {
          width: 100%;
        }
      }
    }
  }
}
</style>
