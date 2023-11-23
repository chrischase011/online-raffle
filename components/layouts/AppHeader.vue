<script lang="ts" setup></script>

<template>
  <nav class="navbar navbar-expand-lg bg-light border-bottom">
    <div class="container">
      <NuxtLink class="navbar-brand" to="/">Online Raffle</NuxtLink>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
        aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <NuxtLink class="nav-link active" aria-current="page" to="/">Raffle</NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped></style>
