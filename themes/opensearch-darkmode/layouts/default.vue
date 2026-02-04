<!-- Default layout: Title and Content -->
<script setup>
import bgDefault from '../assets/theme/bg-default.png'
</script>

<template>
  <div class="slidev-layout default h-full p-12" :style="{ backgroundImage: `url(${bgDefault})` }">
    <slot />
  </div>
</template>

<style scoped>
.default {
  background-size: cover;
  background-position: center;
  color: white;
}
</style>
