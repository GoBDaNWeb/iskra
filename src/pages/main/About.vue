<script setup>
import { Photo } from "@/entities";

import AboutSwiper from "./AboutSwiper.vue";

import photo1 from "@/shared/assets/images/about/1.jpg";
import photo2 from "@/shared/assets/images/about/2.jpg";
import photo3 from "@/shared/assets/images/about/3.jpg";

import { SwiperSlide } from "swiper/vue";
import { MainSwiper } from "@/entities";

const photoList = [
  { id: 1, img: photo1 },
  { id: 2, img: photo2 },
  { id: 3, img: photo3 },
];
</script>

<template>
  <div id="about" class="about">
    <div class="container">
      <div class="about-inner">
        <div class="top">
          <div class="left">
            <Photo
              v-for="photo in photoList"
              :key="photo.img"
              :img="photo.img"
            />
            <div class="swiper-container">
              <MainSwiper :swiperClass="'house-swiper'">
                <SwiperSlide v-for="img in photoList" :key="img.id">
                  <div class="image-wrapper">
                    <img :src="img.img" alt="photo" />
                  </div>
                </SwiperSlide>
              </MainSwiper>
            </div>
          </div>
          <div class="right">
            <h3>О лагере</h3>
            <p>
              Детский оздоровительный лагерь «Искра» ГБУ «Мосгоргеотрест»
              располагается в живописнейшем районе города Красногорска,
              микрорайон Опалиха, в лесной зоне. <br /><br />
              Лагерь стационарный, находится в дубовом бору. Чистейший воздух, в
              жару прохлада от тени дубов, пение птиц, цветы на клумбах и в
              вазонах создают атмосферу сказочного места и дарят нашим детям
              отличный отдых и прекрасное настроение
            </p>
          </div>
        </div>
        <div class="center">
          <div class="image-wrapper">
            <img src="@/shared/assets/images/about/map.png" alt="map" />
          </div>
        </div>
        <div class="bottom">
          <AboutSwiper />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.about {
  padding-top: 156px;
  @media (max-width: $tab) {
    padding-top: 0;
  }
  .about-inner {
    .top {
      display: flex;
      gap: 70px;
      @media (max-width: $tab) {
        flex-direction: column-reverse;
        padding-bottom: 100px;
      }
      .left {
        width: 55%;
        display: flex;
        gap: 34px;
        flex-wrap: wrap;
        align-items: flex-end;
        justify-content: flex-end;
        @media (max-width: $tab) {
          width: 100%;
        }
        .swiper-container {
          display: none;
          width: 100%;
          @media (max-width: $tab) {
            display: block;
          }
          .image-wrapper {
            width: 100%;
            height: 100%;
            border-radius: 15px;
            overflow: hidden;
            img {
              width: 100%;
              height: 100%;
              object-fit: cover;
            }
          }
        }
        .photo {
          @media (max-width: $tab) {
            display: none;
          }
          &:nth-child(1) {
            // aspect-ratio: 3;
            width: calc(50% - 17px);
            aspect-ratio: 2;
            // height: calc(20vw / 2.3);
          }
          &:nth-child(2) {
            width: calc(50% - 17px);
            aspect-ratio: 1.2;
          }
          &:nth-child(3) {
            width: calc(80% - 17px);
            aspect-ratio: 1.5;
          }
        }
      }
      .right {
        width: 45%;
        padding-top: 75px;
        @media (max-width: $tab) {
          width: 100%;
          padding-top: 87px;
        }
        h3 {
          font-weight: 700;
          font-size: 60px;
          line-height: 60px;
          margin-bottom: 32px;
          @media (max-width: $tab) {
            font-size: 40px;
            line-height: 44px;
            margin-bottom: 40px;
          }
        }
        p {
          font-weight: 400;
          font-size: 24px;
          line-height: 36px;
          @media (max-width: $tab) {
            font-size: 18px;
            line-height: 25px;
          }
        }
      }
    }
    .center {
      margin-top: 83px;
      @media (max-width: $tab) {
        display: none;
      }
      .image-wrapper {
        width: 100%;
        height: 100%;
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .bottom {
      margin-bottom: 200px;
      @media (max-width: $tab) {
        display: none;
      }
    }
  }
}
</style>
