<script setup>
import { RouterLink } from "vue-router";
import Nav from "./components/Nav.vue";
</script>

<template>
  <Nav />
  <div>
    <RouterView />
  </div>
</template>

<style>
@import "bulma/css/bulma.min.css";
</style>
