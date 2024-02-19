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
        <span>Навыки</span>
        <ul>
          <li v-for="skill in skills" :key="skill">{{ skill }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.direction-card.right {
  flex-direction: row;
  .left {
    .photo {
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
  .left {
    align-items: flex-start;
    .photo {
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
  .left {
    width: 55%;
    display: flex;
    gap: 34px;
    flex-wrap: wrap;
    align-items: flex-end;
    justify-content: flex-end;
  }
  .right {
    width: 45%;
    .badge {
      width: fit-content;
      padding-left: 50px;
      padding-right: 50px;
      margin-bottom: 23px;
    }
    .content {
      margin-left: 50px;
      p {
        font-weight: 400;
        font-size: 20px;
        line-height: 28px;
        margin-bottom: 35px;
      }
      span {
        font-weight: 400;
        font-size: 20px;
        line-height: 28px;
      }
      ul {
        margin-top: 20px;
        list-style-type: disc;
        li {
          font-weight: 400;
          font-size: 20px;
          line-height: 26px;
          margin-left: 20px;
        }
      }
    }
  }
}
</style>
