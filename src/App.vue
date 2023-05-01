<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="logo">
      <span>CN</span>
      <span>- Sports -</span>
    </div>
    <!-- <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/about">About</RouterLink> -->
  </header>

  <main>
    <RouterView />
  </main>

  <footer>
    <span>Copyright&copy; - 2023</span>
  </footer>
</template>
