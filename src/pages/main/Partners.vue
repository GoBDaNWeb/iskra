<script setup></script>

<template>
  <div class="partners">
    <div class="container">
      <div class="partners-inner">
        <div class="top">
          <h3>Партнеры</h3>
        </div>
        <div class="bottom">
          <div class="partner-item">
            <div class="image-wrapper">
              <img src="@/shared/assets/images/partners/1.png" alt="partner" />
            </div>
          </div>
          <div class="partner-item">
            <div class="image-wrapper">
              <img src="@/shared/assets/images/partners/2.png" alt="partner" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.partners {
  position: relative;
  padding-top: 140px;
  z-index: 3;
  background: var(--beige-color);
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-partners.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-partners-mob.svg");
      background-size: cover;
      background-repeat: no-repeat;
      background-position: right;
    }
  }
  .partners-inner {
    padding-bottom: 90px;
    .top {
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        margin-bottom: 42px;
        @media (max-width: $tab) {
          font-size: 40px;
          line-height: 44px;
        }
      }
    }
    .bottom {
      display: flex;
      align-items: center;
      gap: 30px;
      @media (max-width: $tab) {
        flex-direction: column;
        gap: 15px;
      }
      .partner-item {
        background: var(--white-color);
        border-radius: 12px;
        width: 100%;
        padding: 46px 187px;
        display: flex;
        align-items: center;
        justify-content: center;
        @media (max-width: $tab) {
          padding: 30px 96px;
        }
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
    }
  }
}
</style>
