<script lang="ts" setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="position-relative bottom-0">
    <div class="container">
      <p class="text-center">All Rights Reserved &copy; {{ currentYear }}</p>
    </div>
  </footer>
</template>

<style scoped></style>
