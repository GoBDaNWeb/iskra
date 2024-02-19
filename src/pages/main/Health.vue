<script setup>
import { FileIcon } from "@/shared/icons";
import { Button } from "@/shared/ui";
</script>

<template>
  <div class="health">
    <div class="container">
      <div class="health-inner">
        <div class="left">
          <h3>Забота <br />о здоровье</h3>
          <span
            >Медицинский <br />
            работник 24 часа</span
          >
          <p>Лицензия на меддеятелность</p>
          <div class="file">
            <FileIcon />
            <p>Возможно какое-то описание или пояснение</p>
          </div>
          <Button variable="primary">Посмотреть</Button>
        </div>
        <div class="right">
          <div class="image-wrapper">
            <img src="@/shared/assets/images/health/1.jpg" alt="photo" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.health {
  position: relative;
  background: var(--light-rose-color);
  padding-top: 140px;
  padding-bottom: 108px;
  z-index: 9;
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-health.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
  }
  .health-inner {
    display: flex;
    gap: 94px;
    align-items: flex-end;
    .left {
      width: 36%;
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        margin-bottom: 83px;
      }
      & > span {
        font-weight: 700;
        font-size: 32px;
        line-height: 35px;
        display: block;
        margin-bottom: 50px;
      }
      & > p {
        font-weight: 400;
        font-size: 32px;
        line-height: 38px;
        margin-bottom: 20px;
      }
      .file {
        margin-bottom: 40px;
        display: flex;
        align-items: center;
        gap: 14px;
        svg {
          stroke: var(--black-color);
        }
        p {
          font-weight: 400;
          font-size: 20px;
          line-height: 28px;
        }
      }
      button {
        width: 300px;
      }
    }
    .right {
      width: 58%;
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
}
</style>
