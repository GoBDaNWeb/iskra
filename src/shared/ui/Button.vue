<script setup>
defineProps(["title", "variable", "isLink"]);
</script>

<template>
  <button :class="[variable]">
    <p><slot></slot></p>
  </button>
</template>

<style lang="scss" scoped>
button {
  border-radius: 11px;
  height: 35px;
  padding: 0 20px;
  font-weight: 500;
  font-size: 14px;
  letter-spacing: -7%;
}

button.outline {
  border: 1px solid var(--rose-color);
  transition: var(--trs-300);
  position: relative;
  overflow: hidden;
  color: var(--black-color);
  p {
    position: relative;
    z-index: 2;
  }
  &:before {
    content: "";
    position: absolute;
    background: var(--gradient);
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: 1;
    opacity: 0;
    transition: var(--trs-300);
  }
  &:hover {
    color: var(--white-color);
    border-color: rgba(0, 0, 0, 0);
    &:before {
      opacity: 1;
    }
  }
}

button.primary {
  background: var(--rose-color);
  color: var(--white-color);
  transition: var(--trs-300);
  font-weight: 500;

  font-size: 20px;
  line-height: 24px;
  height: 65px;
  position: relative;
  overflow: hidden;
  p {
    position: relative;
    z-index: 2;
  }

  &:before {
    content: "";
    position: absolute;
    background: var(--gradient);
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: 1;
    opacity: 0;
    transition: var(--trs-300);
  }
  &:hover {
    &:before {
      opacity: 1;
    }
  }
}
</style>
