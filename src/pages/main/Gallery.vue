<script setup>
import { Fancybox } from "@/widgets/fancybox";
import { SwiperSlide } from "swiper/vue";
import { Badge } from "@/shared/ui";
import { DefaultSwiper, Photo } from "@/entities";

import img1 from "@/shared/assets/images/gallery/1.jpg";
import img2 from "@/shared/assets/images/gallery/2.jpg";
import img3 from "@/shared/assets/images/gallery/3.jpg";
import img4 from "@/shared/assets/images/gallery/4.jpg";
import img5 from "@/shared/assets/images/gallery/5.jpg";
import img6 from "@/shared/assets/images/gallery/6.jpg";
import img7 from "@/shared/assets/images/gallery/7.jpg";
import img8 from "@/shared/assets/images/gallery/8.jpg";
import img9 from "@/shared/assets/images/gallery/9.jpg";
import img10 from "@/shared/assets/images/gallery/10.jpg";

const galleryList = [
  {
    img: img1,
  },
  {
    img: img2,
  },
  {
    img: img3,
  },
  {
    img: img4,
  },
  {
    img: img5,
  },
  {
    img: img6,
  },
  {
    img: img7,
  },
  {
    img: img8,
  },
  {
    img: img9,
  },
  {
    img: img10,
  },
];
</script>

<template>
  <div class="gallery">
    <div class="container">
      <div class="gallery-inner">
        <div class="top">
          <h3>Фотогалерея</h3>
        </div>
        <div class="swiper-container">
          <DefaultSwiper>
            <SwiperSlide v-for="img in galleryList" :key="img.id">
              <Photo :img="img.img" />
            </SwiperSlide>
          </DefaultSwiper>
        </div>
        <Fancybox>
          <div class="bottom">
            <Photo
              v-for="img in galleryList"
              :key="img.img"
              :img="img.img"
              :fancy="'gallery'"
            />
          </div>
        </Fancybox>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.gallery {
  position: relative;
  z-index: 6;
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-gallery.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-gallery-mob.svg");
      background-size: cover;
      background-repeat: no-repeat;
    }
  }
  .gallery-inner {
    padding-bottom: 100px;

    .top {
      margin-bottom: 68px;
      @media (max-width: $tab) {
        margin-bottom: 40px;
      }
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        @media (max-width: $tab) {
          font-size: 40px;
          line-height: 44px;
        }
      }
    }
    .swiper-container {
      display: none;
      @media (max-width: 1024px) {
        display: block;
      }
    }
    .bottom {
      display: flex;
      gap: 30px;
      flex-wrap: wrap;
      @media (max-width: $tab) {
        display: none;
      }
      .photo {
        &:nth-child(1) {
          width: calc(50% - 20px);
          aspect-ratio: 1.5;
        }
        &:nth-child(2) {
          width: calc(25% - 20px);
          aspect-ratio: 1.5;
        }
        &:nth-child(3) {
          width: calc(25% - 20px);
          aspect-ratio: 1.5;
        }
        &:nth-child(4) {
          width: calc(25% - 24px);
          aspect-ratio: 1.5;
        }
        &:nth-child(5) {
          width: calc(25% - 24px);
          aspect-ratio: 1.5;
        }
        &:nth-child(6) {
          width: calc(25% - 24px);
          aspect-ratio: 1.5;
        }
        &:nth-child(7) {
          width: calc(25% - 24px);
          aspect-ratio: 1.5;
        }
        &:nth-child(8) {
          width: calc(25% - 24px);
          aspect-ratio: 1.5;
        }
        &:nth-child(9) {
          width: calc(25% - 24px);
          aspect-ratio: 1.5;
        }
        &:nth-child(10) {
          width: calc(50% - 24px);
          aspect-ratio: 1.5;
        }
      }
    }
  }
}
</style>
