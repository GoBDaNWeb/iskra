<script setup>
import { Badge } from "@/shared/ui";
import HeroCard from "./HeroCard.vue";
const heroCardList = [
  {
    id: 1,
    title: "Первая смена",
    date: "01.06.24 — 21.06.24",
    price: "15 000 ₽",
  },
  {
    id: 2,
    title: "Вторая смена",
    date: "01.07.24 — 21.07.24",
    price: "15 000 ₽",
  },
  {
    id: 3,
    title: "Третья смена",
    date: "01.08.24 — 21.08.24",
    price: "15 000 ₽",
  },
];
</script>

<template>
  <div class="hero">
    <div class="hero-images">
      <div class="image-title-wrapper">
        <img src="@/shared/assets/images/title.png" alt="" />
      </div>
      <div class="image-bg-wrapper">
        <!-- <img src="@/shared/assets/images/hero-bg.png" alt="" /> -->
      </div>
      <div class="image-alert-wrapper">
        <img src="@/shared/assets/images/alert.png" alt="" />
      </div>
      <div class="image-main-wrapper"></div>
    </div>
    <div class="hero-inner">
      <div class="container">
        <div class="hero-inner-content">
          <div class="top">
            <h3>Выберите удобные даты</h3>
            <div class="badge-wrapper">
              <Badge variable="outline">7—15 лет</Badge>
              <p>
                <span> 21 день </span> <br />
                длительность смены
              </p>
            </div>
          </div>
          <div class="bottom">
            <HeroCard
              v-for="card in heroCardList"
              :key="card.id"
              :title="card.title"
              :date="card.date"
              :price="card.price"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";
.hero {
  padding-top: 106px;
  min-height: 100vh;
  @media (max-width: $desktop-sm) {
    padding-top: 74px;
  }
  .hero-inner {
    position: relative;
    z-index: 3;
    background: var(--purple-color);
    padding-top: 80px;
    padding-bottom: 100px;
    &:before {
      content: "";
      position: absolute;
      background: url("@/shared/assets/images/shapes/shape-hero1.svg");
      background-size: 100%;
      background-repeat: no-repeat;
      top: -44px;
      width: 100%;
      height: 60px;
      @media (max-width: 1440px) {
        top: -30px;
      }
      @media (max-width: 992px) {
        top: -20px;
      }
      @media (max-width: 660px) {
        top: -10px;
      }
      @media (max-width: $pre-mob) {
        background: url("@/shared/assets/images/shapes/shape-hero1-mob.svg");
        background-size: cover;
        background-repeat: no-repeat;
        top: -50px;
        background-position: right;
      }
    }
    &:after {
      content: "";
      position: absolute;
      background: url("@/shared/assets/images/shapes/shape-hero2.svg");
      background-size: cover;
      background-repeat: no-repeat;
      bottom: -55px;
      width: 100%;
      height: 60px;
      @media (max-width: $tab) {
        background-size: 100%;
      }
      @media (max-width: $pre-mob) {
        background: url("@/shared/assets/images/shapes/shape-hero2-mob.svg");
        background-size: cover;
        background-repeat: no-repeat;
      }
    }
    .hero-inner-content {
      .top {
        display: flex;
        gap: 50px;
        h3 {
          font-weight: 700;
          font-size: 60px;
          line-height: 66px;
          color: var(--white-color);
          @media (max-width: $tab) {
            font-size: 40px;
            line-height: 44px;
          }
        }
        .badge-wrapper {
          display: flex;
          align-items: center;
          gap: 16px;
          @media (max-width: $tab) {
            display: none;
          }
          p {
            font-size: 16px;
            line-height: 19px;
            color: var(--white-color);
            font-weight: 400;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            span {
              font-weight: 700;
            }
          }
        }
      }
      .bottom {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 40px;
        margin-top: 40px;
        @media (max-width: $desktop-sm) {
          grid-template-columns: repeat(2, 1fr);
        }
        @media (max-width: $tab) {
          grid-template-columns: repeat(1, 1fr);
          gap: 25px;
        }
      }
    }
  }
  .hero-images {
    position: relative;
    width: 100%;
    .image-main-wrapper {
      background: url("@/shared/assets/images/hero-bg-main.jpg");
      background-position: top;
      background-size: cover;
      background-repeat: no-repeat;
      padding-top: 106px;
      min-height: 100vh;
      @media (max-width: $mob) {
        background: url("@/shared/assets/images/hero-bg-main-mob.jpg");
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
      }
    }
    .image-alert-wrapper {
      position: absolute;
      width: 289px;
      height: 289px;
      left: 8%;
      top: 60px;
      z-index: 3;
      @media (max-width: $desktop-sm) {
        left: 5%;
      }
      @media (max-width: $tab) {
        display: none;
      }
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .image-bg-wrapper {
      background: url("@/shared/assets/images/hero-bg.png");
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
      position: absolute;
      z-index: 2;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      width: 100%;
      height: 100%;
      @media (max-width: $mob) {
        background: url("@/shared/assets/images/hero-bg-mob.png");
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        top: -7%;
      }
      // img {
      //   width: 100%;
      //   height: 100%;
      //   object-fit: cover;
      // }
    }
    .image-title-wrapper {
      width: 540px;
      height: 330px;
      position: absolute;
      margin: auto;
      left: 0;
      right: 0;
      top: 100px;
      @media (max-width: $desktop-sm) {
        width: 440px;
        height: 282px;
        top: 60px;
      }
      @media (max-width: $mob) {
        width: 350px;
        height: 215px;
        top: 10%;
      }
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
