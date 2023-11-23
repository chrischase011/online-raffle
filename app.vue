<script lang="ts" setup>

useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - Online Raffle` : 'Online Raffle';
  }
})

</script>
<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>