<script setup>
import { SwiperSlide } from "swiper/vue";
import { Button } from "@/shared/ui";
import image from "@/shared/assets/images/house/1.jpg";
import { MainSwiper } from "@/entities";
const houseList = [
  { id: 1, img: image },
  { id: 2, img: image },
  { id: 3, img: image },
  { id: 4, img: image },
];
</script>

<template>
  <div id="house" class="house">
    <div class="container">
      <div class="house-inner">
        <div class="left">
          <h3>Комфортное проживание</h3>
          <p>8 комфортабельных <br />корпусов</p>
          <ul>
            <li>Общая вместимость: 270 человек</li>
            <li>Условия размещения: 2-5 человек в комнате</li>
            <li>Удобства в каждой комнате</li>
          </ul>
          <Button variable="primary">Правила бронирования</Button>
        </div>
        <div class="right">
          <MainSwiper :swiperClass="'house-swiper'">
            <SwiperSlide v-for="img in houseList" :key="img.id">
              <div class="image-wrapper">
                <img :src="img.img" alt="photo" />
              </div>
            </SwiperSlide>
          </MainSwiper>
          <div class="button-wrapper">
            <Button variable="primary">Правила бронирования</Button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.house-swiper {
  .swiper-pagination-bullet {
    width: 15px;
    height: 15px;
    background: var(--yellow-color);
    opacity: 1;
  }
  .swiper-pagination-bullet-active {
    background: var(--purple-color);
  }
}
</style>
<style lang="scss" scoped>
@import "@/shared/styles/vars";

.house {
  position: relative;
  background: var(--beige-color);
  z-index: 11;
  &:before {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-house1.svg");
    background-size: 100.5%;
    background-repeat: no-repeat;
    top: -40px;
    width: 100%;
    height: 60px;
    @media (max-width: 1440px) {
      top: -30px;
    }
    @media (max-width: 992px) {
      top: -20px;
    }

    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-house1-mob.svg");
      background-size: cover;
      background-position: right;
      background-repeat: no-repeat;
      top: -45px;
    }
  }
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-house2.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab) {
      background-size: 100%;
    }
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-house2-mob.svg");
      background-size: cover;
      background-repeat: no-repeat;
    }
  }

  .house-inner {
    padding-top: 104px;
    padding-bottom: 104px;
    display: flex;
    gap: 94px;
    align-items: flex-end;
    @media (max-width: $desktop-sm) {
      gap: 30px;
    }
    @media (max-width: $tab) {
      flex-direction: column;
      padding-bottom: 62px;
      padding-top: 50px;
    }
    .left {
      width: 42%;
      @media (max-width: $tab) {
        width: 100%;
      }
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        margin-bottom: 32px;
        @media (max-width: $tab) {
          font-size: 40px;
          line-height: 44px;
          margin-bottom: 40px;
        }
      }
      p {
        font-weight: 400;
        font-size: 32px;
        line-height: 38px;
        margin-bottom: 40px;
        @media (max-width: $tab) {
          font-size: 28px;
          line-height: 33px;
        }
      }
      ul {
        list-style-type: disc;
        margin-bottom: 50px;
        @media (max-width: $tab) {
          margin-bottom: 0;
        }
        li {
          margin-left: 20px;
          font-weight: 400;
          font-size: 20px;
          line-height: 26px;
          @media (max-width: $tab) {
            font-size: 18px;
            line-height: 23px;
          }
        }
      }
      button {
        width: 330px;
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
      .button-wrapper {
        display: none;
        @media (max-width: $tab) {
          display: flex;
          justify-content: center;
          align-items: center;
          margin-top: 65px;
          button {
            width: 360px;
          }
        }
      }
    }
  }
}
</style>
