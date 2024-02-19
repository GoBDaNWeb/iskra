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
        <img src="@/shared/assets/images/hero-bg.png" alt="" />
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
.hero {
  padding-top: 106px;
  min-height: 100vh;
  margin-bottom: 156px;
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
      background-size: contain;
      background-repeat: no-repeat;
      top: -40px;
      width: 100%;
      height: 60px;
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
        }
        .badge-wrapper {
          display: flex;
          align-items: center;
          gap: 16px;
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
        display: flex;
        gap: 40px;
        margin-top: 40px;
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
    }
    .image-alert-wrapper {
      position: absolute;
      width: 289px;
      height: 289px;
      left: 8%;
      top: 60px;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .image-bg-wrapper {
      position: absolute;
      z-index: 2;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      width: 100%;
      height: 100%;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .image-title-wrapper {
      width: 540px;
      height: 330px;
      position: absolute;
      margin: auto;
      left: 0;
      right: 0;
      top: 100px;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
