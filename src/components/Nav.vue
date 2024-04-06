<script setup>
import { ref } from "vue";
const showNavMenu = ref(false);
</script>
<template>
  <nav class="navbar is-info" role="navigation" aria-label="main navigation">
    <div class="container px-2">
      <div class="navbar-brand">
        <RouterLink
          :to="{ name: 'notes' }"
          class="navbar-item is-size-4 is-family-monospace"
        >
          NotesList
        </RouterLink>

        <a
          role="button"
          class="navbar-burger"
          :class="{ 'is-active': showNavMenu }"
          @click.prevent="showNavMenu = !showNavMenu"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div
        id="navbarBasicExample"
        :class="{ 'is-active': showNavMenu }"
        class="navbar-menu"
      >
        <div class="navbar-end">
          <RouterLink
            class="navbar-item"
            active-class="is-active"
            :to="{ name: 'notes' }"
          >
            Notes
          </RouterLink>
          <RouterLink
            class="navbar-item"
            active-class="is-active"
            :to="{ name: 'stats' }"
          >
            Stats
          </RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>
<style scoped>
@media (max-width: 1023px) {
  .navbar-menu {
    position: absolute;
    left: 0;
    right: 0;
  }
}
</style>
