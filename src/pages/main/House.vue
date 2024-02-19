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
  <div class="house">
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
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.house-swiper {
  .swiper-pagination-bullet {
    width: 15px !important;
    height: 15px !important;
    background: var(--yellow-color) !important;
    opacity: 1;
  }
  .swiper-pagination-bullet-active {
    background: var(--purple-color) !important;
  }
}
</style>
<style lang="scss" scoped>
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
  }

  .house-inner {
    padding-top: 104px;
    padding-bottom: 104px;
    display: flex;
    gap: 94px;
    align-items: flex-end;
    .left {
      width: 42%;
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        margin-bottom: 32px;
      }
      p {
        font-weight: 400;
        font-size: 32px;
        line-height: 38px;
        margin-bottom: 40px;
      }
      ul {
        list-style-type: disc;
        margin-bottom: 50px;
        li {
          margin-left: 20px;
          font-weight: 400;
          font-size: 20px;
          line-height: 26px;
        }
      }
      button {
        width: 330px;
      }
    }
    .right {
      width: 58%;
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
  }
}
</style>
