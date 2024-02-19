<script setup>
import { FileIcon } from "@/shared/icons";
import { Button } from "@/shared/ui";

defineProps(["title", "text"]);
</script>

<template>
  <div class="document-item">
    <div class="content">
      <h6>{{ title }}</h6>
      <div class="file">
        <FileIcon />
        <p>
          {{ text }}
        </p>
      </div>
    </div>

    <Button variable="primary">Посмотреть</Button>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.document-item {
  padding: 47px 30px;
  background: var(--white-color);
  border-radius: 12px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 20px;
  height: 340px;
  @media (max-width: $tab) {
    padding: 37px 30px;
  }
  h6 {
    font-weight: 400;
    font-size: 32px;
    line-height: 28px;
    color: var(--black-color);
    margin-bottom: 20px;
  }
  .file {
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
      color: var(--black-color);
    }
  }
  button {
    width: 300px;
    @media (max-width: $mob) {
      width: 100%;
    }
  }
}
</style>
