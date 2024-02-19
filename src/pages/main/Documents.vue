<script setup>
import { SwiperSlide } from "swiper/vue";
import DocumentItem from "./DocumentItem.vue";
import { TripleSwiper, Photo } from "@/entities";

const documentsList = [
  {
    id: 1,
    title: "Устав МГГТ",
    text: "Возможно какое-то описание или пояснение",
  },
  {
    id: 2,
    title: "Положение о ДОЛ «Искра»",
    text: "Возможно какое-то описание или пояснение",
  },
  {
    id: 3,
    title: "Лицензия на меддеятелность",
    text: "Возможно какое-то описание или пояснение",
  },
  {
    id: 4,
    title: "Устав МГГТ",
    text: "Возможно какое-то описание или пояснение",
  },
  {
    id: 5,
    title: "Устав МГГТ",
    text: "Возможно какое-то описание или пояснение",
  },
];
</script>

<template>
  <div id="documents" class="documents">
    <div class="documents-wrapper">
      <div class="container">
        <div class="documents-inner">
          <div class="top">
            <h3>Документы</h3>
          </div>
          <div class="bottom">
            <TripleSwiper pagColor="purple">
              <SwiperSlide v-for="document in documentsList" :key="document.id">
                <DocumentItem :title="document.title" :text="document.text" />
              </SwiperSlide>
            </TripleSwiper>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.documents {
  padding-top: 140px;
  position: relative;
  z-index: 4;
  background: var(--lavand-color);
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-documents.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-documents-mob.svg");
      background-size: cover;
      background-repeat: no-repeat;
    }
  }
  .documents-wrapper {
    overflow: hidden;
  }
  .documents-inner {
    padding-bottom: 91px;
    .top {
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
    .bottom {
      margin-top: 66px;
    }
  }
}
</style>
