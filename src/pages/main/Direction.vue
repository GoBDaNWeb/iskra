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
              <h3>Развивающие направления</h3>
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
.direction {
  background-color: var(--yellow-color);
  background-image: url("@/shared/assets/images/direction/bg.png");
  background-position: top;
  background-size: cover;
  background-repeat: no-repeat;
  position: relative;
  z-index: 8;
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-direction.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
  }
  .direction-wrapper {
    overflow: hidden;
  }
  .direction-inner {
    padding-top: 130px;
    padding-bottom: 100px;

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
        h3 {
          font-weight: 700;
          font-size: 60px;
          line-height: 66px;
          background-image: var(--gradient);
          color: transparent;
          -webkit-background-clip: text;
          background-clip: text;
        }
        p {
          font-weight: 400;
          font-size: 24px;
          line-height: 36px;
        }
      }
    }
    .bottom {
      margin-top: 233px;
    }
  }
}
</style>
