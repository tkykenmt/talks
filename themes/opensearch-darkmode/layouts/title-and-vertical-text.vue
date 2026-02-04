<!-- Title and Vertical Text layout -->
<script setup>
import bgDefault from '../assets/theme/bg-default.png'
</script>

<template>
  <div class="slidev-layout title-and-vertical-text h-full p-12" :style="{ backgroundImage: `url(${bgDefault})` }">
    <slot />
  </div>
</template>

<style scoped>
.title-and-vertical-text {
  background-size: cover;
  background-position: center;
  color: white;
}
</style>
