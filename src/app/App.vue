<script setup>
import { RouterLink, RouterView } from "vue-router";
import { Header } from "@/widgets/header";
import { Footer } from "@/widgets/footer";
import { MobileMenu } from "@/widgets/mobile-menu";
</script>

<template>
  <Header />
  <MobileMenu />
  <RouterView />
  <Footer />
</template>

<style lang="scss">
@import "@/shared/styles/fonts";
</style>
