<script setup>
import DirectionSwiper from "./DirectionSwiper.vue";
</script>

<template>
  <div class="direction">
    <div class="direction-wrapper">
      <div class="container">
        <div class="direction-inner">
          <div class="top">
            <div class="direction-about">
              <div class="title-wrapper">
                <h3>Развивающие направления</h3>
              </div>
              <p>
                При попадании в лагерь каждый ребенок может выбрать одно из пяти
                направлений познавательного досуга, которое закрепляется за
                ребенком на время смены
              </p>
            </div>
          </div>
          <div class="bottom">
            <DirectionSwiper />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.direction {
  background-color: var(--yellow-color);
  background-image: url("@/shared/assets/images/direction/bg.png");
  background-position: top;
  background-size: cover;
  background-repeat: no-repeat;
  position: relative;
  z-index: 8;
  @media (max-width: $tab) {
    background-image: url("@/shared/assets/images/direction/bg-mob.png");
    background-position: top;
    background-size: cover;
    background-repeat: no-repeat;
  }
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-direction.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-direction-mob.svg");
      background-size: cover;
      background-repeat: no-repeat;
    }
  }
  .direction-wrapper {
    overflow: hidden;
  }
  .direction-inner {
    padding-top: 130px;
    padding-bottom: 100px;
    @media (max-width: $tab) {
      padding-top: 303px;
    }

    .top {
      .direction-about {
        max-width: 776px;
        margin: auto;
        display: flex;
        flex-direction: column;
        gap: 44px;
        background: url("@/shared/assets/images/direction/rectange.svg");
        background-size: contain;
        background-position: center;
        padding: 36px 40px 50px 57px;
        background-repeat: no-repeat;
        @media (max-width: $tab) {
          background: none;
          padding: 0;
        }
        .title-wrapper {
          @media (max-width: $tab) {
            background: var(--white-color);
            padding: 19px 20px 30px 24px;
            border-radius: 20px;
          }
        }
        h3 {
          font-weight: 700;
          font-size: 60px;
          line-height: 66px;
          background-image: var(--gradient);
          color: transparent;
          -webkit-background-clip: text;
          background-clip: text;
          position: relative;
          @media (max-width: $tab) {
            font-size: 40px;
            line-height: 44px;
          }
        }
        p {
          font-weight: 400;
          font-size: 24px;
          line-height: 36px;
          @media (max-width: $tab) {
            font-size: 18px;
            line-height: 25px;
            padding-left: 30px;
          }
        }
      }
    }
    .bottom {
      margin-top: 233px;
      @media (max-width: $tab) {
        margin-top: 40px;
      }
    }
  }
}
</style>
