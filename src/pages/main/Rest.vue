<script setup>
import { Photo } from "@/entities";
import { Button } from "@/shared/ui";
import { FileIcon } from "@/shared/icons";
import RestSwiper from "./RestSwiper.vue";

import img from "@/shared/assets/images/rest/1.jpg";
</script>

<template>
  <div id="rest" class="rest">
    <div class="rest-wrapper">
      <div class="container">
        <div class="rest-inner">
          <div class="top">
            <div class="left">
              <h3>Досуг</h3>
              <p>
                Благодаря большому разнообразию развлечений один день ребенка в
                лагере никогда не похож на другой.
              </p>
              <span>Распорядок дня</span>
              <div class="file">
                <FileIcon />
                <p>Вы можете ознакомиться с примером расписания</p>
              </div>
              <Button variable="primary">Посмотреть</Button>
            </div>
            <div class="right">
              <Photo :img="img" />
              <!-- <div class="image-wrapper">
              <img src="@/shared/assets/images/rest/1.jpg" alt="photo" />
            </div> -->
            </div>
          </div>
          <div class="bottom"><RestSwiper /></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.rest {
  background: var(--purple-color);
  position: relative;
  z-index: 7;
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-rest.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
    @media (max-width: $tab-sm) {
      background: url("@/shared/assets/images/shapes/shape-rest-mob.svg");
      background-size: cover;

      background-repeat: no-repeat;
    }
  }
  .rest-wrapper {
    overflow: hidden;
  }
  .rest-inner {
    padding-top: 140px;
    padding-bottom: 125px;
    @media (max-width: $tab) {
      padding-bottom: 85px;
    }
    .top {
      display: flex;
      gap: 94px;
      align-items: center;
      .left {
        width: 36%;
        @media (max-width: $tab) {
          width: 100%;
        }
        h3 {
          color: var(--white-color);
          font-weight: 700;
          font-size: 60px;
          line-height: 66px;
          margin-bottom: 42px;
          @media (max-width: $tab) {
            font-size: 40px;
            line-height: 44px;
            margin-bottom: 40px;
          }
        }
        & > p {
          font-weight: 400;
          font-size: 24px;
          line-height: 36px;
          color: var(--white-color);
          margin-bottom: 50px;
          @media (max-width: $tab) {
            font-size: 18px;
            line-height: 25px;
          }
        }
        span {
          font-weight: 400;
          font-size: 32px;
          line-height: 38px;
          color: var(--white-color);
          display: block;
          margin-bottom: 30px;
        }
        .file {
          display: flex;
          align-items: center;
          gap: 14px;
          svg {
            stroke: var(--white-color);
          }
          p {
            color: var(--white-color);
            font-weight: 400;
            font-size: 20px;
            line-height: 28px;
            @media (max-width: $tab) {
              font-size: 18px;
              line-height: 25px;
              max-width: 263px;
            }
          }
        }
        button {
          margin-top: 40px;
          width: 300px;
          @media (max-width: $pre-mob) {
            width: 100%;
          }
        }
      }
      .right {
        width: 58%;
        @media (max-width: $tab) {
          display: none;
        }
        .image-wrapper {
          width: 100%;
          height: calc(20vw * 1.1);
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
    .bottom {
      margin-top: 94px;
      @media (max-width: $tab) {
        margin-top: 40px;
      }
    }
  }
}
</style>
