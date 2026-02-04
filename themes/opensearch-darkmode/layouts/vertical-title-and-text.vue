<!-- Vertical Title and Text layout -->
<script setup>
import bgVertical from '../assets/theme/bg-vertical-title-and-text.png'
</script>

<template>
  <div class="slidev-layout vertical-title-and-text h-full p-12" :style="{ backgroundImage: `url(${bgVertical})` }">
    <slot />
  </div>
</template>

<style scoped>
.vertical-title-and-text {
  background-size: cover;
  background-position: center;
  color: white;
}
</style>
