<script setup>
defineProps(["img", "fancy"]);
</script>

<template>
  <div class="photo">
    <a v-if="fancy" :data-fancybox="fancy" :href="img">
      <div class="image-wrapper">
        <img :src="img" alt="photo" />
      </div>
    </a>
    <div v-else class="image-wrapper">
      <img :src="img" alt="photo" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.photo {
  position: relative;
  transition: var(--trs-300);
  &:before {
    content: "";
    width: 100%;
    height: 100%;
    background: var(--yellow-color);
    position: absolute;
    bottom: -5px;
    border-radius: 14px;
    z-index: 1;
    left: -5px;
  }
  .image-wrapper {
    z-index: 2;
    position: relative;
    border-radius: 15px;
    overflow: hidden;
    width: 100%;
    height: 100%;
    a {
      width: 100%;
      height: 100%;
      position: relative;
      display: block;
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>
