<script setup>
import { Photo } from "@/entities";
import { Badge } from "@/shared/ui";
defineProps(["textDirection", "title", "imgs", "text", "skills"]);
</script>

<template>
  <div class="direction-card" :class="textDirection">
    <div class="left">
      <Photo v-for="img in imgs" :key="img" :img="img" />
    </div>
    <div class="right">
      <Badge variable="primary">{{ title }}</Badge>
      <div class="content">
        <p>{{ text }}</p>
        <Photo :img="imgs[0]" />
        <span>Навыки</span>
        <ul>
          <li v-for="skill in skills" :key="skill">{{ skill }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.direction-card.right {
  flex-direction: row;
  @media (max-width: $tab) {
    flex-direction: column-reverse;
  }
  .left {
    .photo {
      @media (max-width: $tab) {
        display: none;
      }
      aspect-ratio: 1.2;
      &:nth-child(1) {
        flex: 1 1 30%;
        max-height: 146px;
      }
      &:nth-child(2) {
        flex: 1 1 35%;
      }
      &:nth-child(3) {
        flex: 1 1 40%;

        max-width: 80%;
        max-height: 270px;
      }
    }
  }
}
.direction-card.left {
  flex-direction: row-reverse;
  @media (max-width: $tab) {
    flex-direction: column-reverse;
  }
  .left {
    align-items: flex-start;
    .photo {
      @media (max-width: $tab) {
        display: none;
      }
      aspect-ratio: 1.2;
      &:nth-child(1) {
        flex: 1 1 100%;
        max-height: 280px;
      }
      &:nth-child(2) {
        flex: 1 1 35%;
        max-height: 150px;
        margin-left: 30px;
      }
      &:nth-child(3) {
        flex: 1 1 30%;

        max-height: 270px;
      }
    }
  }
}
.direction-card {
  border-radius: 24px;
  background: var(--white-color);
  display: flex;
  align-items: flex-start;
  gap: 43px;
  padding: 104px 54px 103px 47px;
  aspect-ratio: 1.5;
  height: 100%;
  width: 100%;
  @media (max-width: $tab) {
    padding: 25px;
    justify-content: flex-end;
  }
  .left {
    width: 55%;
    display: flex;
    gap: 34px;
    flex-wrap: wrap;
    align-items: flex-end;
    justify-content: flex-end;
    @media (max-width: $tab) {
      width: 100%;
    }
  }
  .right {
    width: 45%;
    .photo {
      display: none;
    }
    @media (max-width: $tab) {
      width: 100%;
      .photo {
        display: block;
        height: calc(20vw * 2);
        margin-bottom: 23px;
      }
    }
    .badge {
      width: fit-content;
      padding-left: 50px;
      padding-right: 50px;
      margin-bottom: 23px;
      @media (max-width: $tab) {
        padding-left: 15px;
        padding-right: 15px;
      }
    }
    .content {
      margin-left: 50px;
      @media (max-width: $tab) {
        margin-left: 0;
      }
      p {
        font-weight: 400;
        font-size: 20px;
        line-height: 28px;
        margin-bottom: 35px;
        @media (max-width: $tab) {
          font-size: 14px;
          line-height: 19px;
        }
      }
      span {
        font-weight: 400;
        font-size: 20px;
        line-height: 28px;
        @media (max-width: $tab) {
          font-size: 14px;
          line-height: 19px;
        }
      }
      ul {
        margin-top: 20px;
        list-style-type: disc;

        li {
          font-weight: 400;
          font-size: 20px;
          line-height: 26px;
          margin-left: 20px;
          @media (max-width: $tab) {
            font-size: 14px;
            line-height: 19px;
          }
        }
      }
    }
  }
}
</style>
