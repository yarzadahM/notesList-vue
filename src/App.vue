<script setup>
import { RouterLink } from "vue-router";
import Nav from "./components/Nav.vue";
</script>

<template>
  <Nav />
  <div class="container px-3">
    <RouterView />
  </div>
</template>

<style>
@import "bulma/css/bulma.min.css";
</style>
