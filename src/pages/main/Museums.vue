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
          <h3>Дополнительное образование</h3>
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
    .top {
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
      }
    }
    .bottom {
      display: grid;
      grid-template-columns: repeat(2, calc(50% - 15px));
      gap: 30px;
      margin-top: 48px;
      .museums-item {
        width: 100%;
      }
    }
  }
}
</style>
