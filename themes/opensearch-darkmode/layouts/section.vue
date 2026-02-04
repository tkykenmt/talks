<!-- Section layout: Section Header -->
<script setup>
import bgDefault from '../assets/theme/bg-default.png'
</script>

<template>
  <div class="slidev-layout section h-full flex flex-col justify-end pb-32 pl-12" :style="{ backgroundImage: `url(${bgDefault})` }">
    <slot />
  </div>
</template>

<style scoped>
.section {
  background-size: cover;
  background-position: center;
  color: white;
}
.section :deep(h1) {
  font-size: 3.5rem;
  font-weight: 400;
}
.section :deep(p) {
  color: #7eb8c9;
}
</style>
