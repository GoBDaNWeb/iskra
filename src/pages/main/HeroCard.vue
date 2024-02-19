<script setup>
import { Button } from "@/shared/ui";

defineProps(["title", "date", "price"]);
</script>

<template>
  <div class="hero-card">
    <div class="hero-card-content">
      <h5>{{ title }}</h5>
      <p>{{ date }}</p>
      <span>{{ price }}</span>
      <div class="button-wrapper">
        <Button variable="primary">Забронировать</Button>
        <Button variable="outline">Программа смены</Button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.hero-card {
  position: relative;
  z-index: 2;
  width: 100%;
  &:before {
    content: "";
    width: 102%;
    height: 103%;
    background: var(--yellow-color);
    position: absolute;
    bottom: -7px;
    border-radius: 14px;
    z-index: 1;
    left: -7px;
  }
  .hero-card-content {
    background: var(--white-color);
    border-radius: 11px;
    padding: 27px 32px 37px;
    position: relative;
    z-index: 2;
    display: flex;
    flex-direction: column;
    gap: 15px;
    h5 {
      font-weight: 700;
      font-size: 32px;
      line-height: 35px;
    }
    p {
      font-weight: 400;
      font-size: 20px;
      line-height: 28px;
      @media (max-width: $tab) {
        font-size: 18px;
        line-height: 25px;
      }
    }
    span {
      font-weight: 700;
      font-size: 28px;
      line-height: 34px;
    }
    .button-wrapper {
      display: flex;
      gap: 10px;
      align-items: center;
      @media (max-width: $tab) {
        flex-direction: column;
      }
      button {
        font-size: 14px;
        line-height: 16px;
        height: 45px;
        @media (max-width: $tab) {
          width: 286px;
        }
        @media (max-width: $pre-mob) {
          width: 100%;
        }
      }
    }
  }
}
</style>
