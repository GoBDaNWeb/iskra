<script setup>
import { SwiperSlide } from "swiper/vue";
import { Badge } from "@/shared/ui";
import { DefaultSwiper, Photo } from "@/entities";

import img1 from "@/shared/assets/images/education/1.jpg";
import img2 from "@/shared/assets/images/education/2.jpg";
const educationList1 = [
  { id: 1, img: img1 },
  { id: 2, img: img1 },
  { id: 3, img: img1 },
];
const educationList2 = [
  { id: 1, img: img2 },
  { id: 2, img: img2 },
  { id: 3, img: img2 },
];
</script>

<template>
  <div class="education">
    <div class="container">
      <div class="education-inner">
        <div class="top">
          <h3>Дополнительное образование</h3>
        </div>
        <div class="center">
          <div class="education-item">
            <DefaultSwiper
              :title="'Зазеркалье'"
              :badges="['витраж', 'декупаж']"
            >
              <SwiperSlide v-for="img in educationList1" :key="img.id">
                <Photo :img="img.img" />
              </SwiperSlide>
            </DefaultSwiper>
          </div>
          <div class="education-item">
            <DefaultSwiper
              :title="'Волшебная иголочка'"
              :badges="['шитье, вышивание', 'поделки']"
            >
              <SwiperSlide v-for="img in educationList2" :key="img.id">
                <Photo :img="img.img" />
              </SwiperSlide>
            </DefaultSwiper>
          </div>
        </div>
        <div class="bottom">
          <div class="education-about">
            <h4>Каждый сезон меняется набор кружков</h4>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.education {
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
  .education-inner {
    padding-top: 140px;
    .top {
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
      }
    }
    .center {
      display: flex;
      align-items: center;
      gap: 30px;
      margin-top: 48px;
      .education-item {
        width: 50%;
      }
    }
    .bottom {
      padding-top: 50px;
      .education-about {
        background: url("@/shared/assets/images/education/rectangle.png");
        background-size: contain;
        background-position: center;
        padding: 114px 62px 117px;
        background-repeat: no-repeat;
        max-width: 815px;
        margin: auto;
        h4 {
          font-weight: 700;
          font-size: 32px;
          line-height: 35px;
          background-image: var(--gradient);
          color: transparent;
          -webkit-background-clip: text;
          background-clip: text;
        }
      }
    }
  }
}
</style>
