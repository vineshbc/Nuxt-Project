<!-- Please remove this file from your project -->
<template>
  <div class="nav">
    <nav class="nav-bar">
      <div class="nav--logo">
        <NuxtLink :to="{ name: 'index' }" class="nav--text">
          <img src="../static/nuxt.png" alt="logo" class="img"
        /></NuxtLink>
      </div>
      <div class="nav--link">
        <NuxtLink :to="{ name: 'about' }" class="nav--text">About</NuxtLink>
        <NuxtLink :to="{ name: 'contact' }" class="nav--text">Contact</NuxtLink>
        <NuxtLink :to="{ name: 'test' }" class="nav--text">Test</NuxtLink>
      </div>
    </nav>
  </div>
</template>

<style scoped>
</style>