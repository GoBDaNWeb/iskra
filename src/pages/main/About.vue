<script setup>
import { Photo } from "@/entities";

import AboutSwiper from "./AboutSwiper.vue";

import photo1 from "@/shared/assets/images/about/1.jpg";
import photo2 from "@/shared/assets/images/about/2.jpg";
import photo3 from "@/shared/assets/images/about/3.jpg";

const photoList = [{ img: photo1 }, { img: photo2 }, { img: photo3 }];
</script>

<template>
  <div class="about">
    <div class="container">
      <div class="about-inner">
        <div class="top">
          <div class="left">
            <Photo
              v-for="photo in photoList"
              :key="photo.img"
              :img="photo.img"
            />
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
.about {
  .about-inner {
    .top {
      display: flex;
      gap: 70px;
      .left {
        width: 55%;
        display: flex;
        gap: 34px;
        flex-wrap: wrap;
        align-items: flex-end;
        justify-content: flex-end;
        .photo {
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
        h3 {
          font-weight: 700;
          font-size: 60px;
          line-height: 60px;
          margin-bottom: 32px;
        }
        p {
          font-weight: 400;
          font-size: 24px;
          line-height: 36px;
        }
      }
    }
    .center {
      margin-top: 83px;
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
    }
  }
}
</style>
