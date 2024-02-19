<script setup>
defineProps(["variable"]);
</script>

<template>
  <div class="badge" :class="[variable]">
    <slot></slot>
  </div>
</template>

<style lang="scss" scoped>
.badge {
  border-radius: 10px;
  padding: 12px 14px;
}
.badge.outline {
  background: none;
  border: 1px solid var(--white-color);
  color: var(--white-color);
  font-size: 16px;
  font-weight: 400;
  line-height: 19px;
}
.badge.primary {
  background: rgb(255, 175, 0);
  background: var(--gradient);
  color: var(--white-color);
  font-size: 36px;
  font-weight: 500;
  line-height: 54px;
  border-radius: 51px;
}
</style>
