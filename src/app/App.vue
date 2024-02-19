<script setup>
import { RouterLink, RouterView } from "vue-router";
import { Header } from "@/widgets/header";
import { Footer } from "@/widgets/footer";
</script>

<template>
  <Header />

  <RouterView />
  <Footer />
</template>
