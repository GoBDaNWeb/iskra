<script setup>
import { SwiperSlide } from "swiper/vue";
import { Button } from "@/shared/ui";
import image from "@/shared/assets/images/nutrition/1.jpg";
import { MainSwiper } from "@/entities";
import { FileIcon } from "@/shared/icons";
const houseList = [
  { id: 1, img: image },
  { id: 2, img: image },
  { id: 3, img: image },
  { id: 4, img: image },
];
</script>

<template>
  <div id="nutrition" class="nutrition">
    <div class="container">
      <div class="nutrition-inner">
        <div class="left">
          <h3>Полноценное питание</h3>
          <span>Пример меню</span>
          <div class="menu">
            <FileIcon />
            <p>Полезное, 6-разовое питание из качественных ингредиентов</p>
          </div>
          <Button variable="primary">Посмотреть</Button>
        </div>
        <div class="right">
          <MainSwiper :swiperClass="'nutrition-swiper'">
            <SwiperSlide v-for="img in houseList" :key="img.id">
              <div class="image-wrapper">
                <img :src="img.img" alt="photo" />
              </div>
            </SwiperSlide>
          </MainSwiper>
          <div class="menu-wrapper">
            <span>Пример меню</span>
            <div class="menu-mob">
              <FileIcon />
              <p>Полезное, 6-разовое питание из качественных ингредиентов</p>
            </div>
          </div>

          <div class="button-wrapper">
            <Button variable="primary">Посмотреть</Button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.nutrition-swiper {
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

.nutrition {
  background: var(--purple-color);
  position: relative;
  z-index: 10;
  padding-top: 165px;
  padding-bottom: 100px;
  @media (max-width: $tab) {
    padding-top: 88px;
    padding-bottom: 60px;
  }
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-nutrition.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-nutrition-mob.svg");
      background-size: cover;
      background-repeat: no-repeat;
      background-position: right;
    }
  }
  .nutrition-inner {
    display: flex;
    gap: 94px;
    @media (max-width: $desktop-sm) {
      gap: 30px;
    }
    @media (max-width: $tab) {
      flex-direction: column;
    }
    .left {
      width: 42%;
      @media (max-width: $tab) {
        width: 100%;
      }
      h3 {
        font-weight: 700;
        color: var(--white-color);
        font-size: 60px;
        line-height: 66px;
        margin-bottom: 46px;
        @media (max-width: $tab) {
          font-size: 40px;
          line-height: 44px;
          margin-bottom: 40px;
        }
      }
      span {
        font-weight: 400;
        font-size: 32px;
        line-height: 38px;
        color: var(--white-color);
        margin-bottom: 20px;
        display: block;
        @media (max-width: $tab) {
          display: none;
        }
      }
      .menu {
        display: flex;
        align-items: center;
        gap: 14px;
        margin-bottom: 20px;
        @media (max-width: $tab) {
          display: none;
        }
        svg {
          stroke: var(--white-color);
        }
        p {
          font-weight: 400;
          font-size: 20px;
          line-height: 28px;
          color: var(--white-color);
          @media (max-width: $tab) {
            font-size: 18px;
            line-height: 25px;
            max-width: 263px;
          }
        }
      }
      button {
        width: 255px;
        @media (max-width: $tab) {
          display: none;
        }
      }
    }
    .right {
      width: 58%;
      @media (max-width: $tab) {
        width: 100%;
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
      .menu-wrapper {
        display: none;

        @media (max-width: $tab) {
          display: flex;
          flex-direction: column;
          gap: 40px;
          margin-top: 104px;
        }
        span {
          font-size: 28px;
          line-height: 33px;
          color: var(--white-color);
        }
        .menu-mob {
          align-items: center;
          gap: 14px;
          display: flex;
          svg {
            stroke: var(--white-color);
          }
          p {
            color: var(--white-color);
            font-size: 18px;
            line-height: 25px;
            max-width: 263px;
          }
        }
      }

      .button-wrapper {
        display: none;
        @media (max-width: $tab) {
          display: flex;
          justify-content: center;
          align-items: center;
          margin-top: 40px;
          button {
            width: 360px;
          }
        }
      }
    }
  }
}
</style>
