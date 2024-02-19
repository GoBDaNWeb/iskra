<script setup>
import { Accordion } from "@/shared/ui";
</script>

<template>
  <div class="faq">
    <div class="container">
      <div class="faq-inner">
        <h3>Вопрос/ответ</h3>
        <div class="faq-list">
          <Accordion />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.faq {
  background: var(--yellow-color);
  position: relative;
  z-index: 5;
  padding-top: 140px;
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-faq.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-faq-mob.svg");
      background-size: cover;
      background-repeat: no-repeat;
      background-position: right;
    }
  }
  .faq-inner {
    padding-bottom: 82px;
    h3 {
      font-weight: 700;
      font-size: 60px;
      line-height: 66px;
      @media (max-width: $tab) {
        font-size: 40px;
        line-height: 44px;
      }
    }
    .faq-list {
      margin-top: 42px;
      display: flex;
      flex-direction: column;
      gap: 24px;
      @media (max-width: $tab) {
        gap: 15px;
      }
    }
  }
}
</style>
