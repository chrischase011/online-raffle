<script lang="ts" setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="bottom-0 position-relative">
    <div class="container">
      <p class="text-center">&copy; {{ currentYear }}</p>
    </div>
  </footer>
</template>

<style scoped></style>
