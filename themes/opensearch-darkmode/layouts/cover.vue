<!-- Cover layout: Title Slide -->
<script setup>
import bgCover from '../assets/theme/bg-cover.png'

defineProps({
  subtitle: String,
  author: String,
})
</script>

<template>
  <div class="slidev-layout cover h-full flex flex-col justify-center items-end text-right pr-16" :style="{ backgroundImage: `url(${bgCover})` }">
    <slot />
    <p v-if="subtitle" class="text-xl opacity-80 mt-4">{{ subtitle }}</p>
    <p v-if="author" class="text-base opacity-60 mt-8">{{ author }}</p>
  </div>
</template>

<style scoped>
.cover {
  background-size: cover;
  background-position: center;
  color: var(--slidev-theme-lt1, white);
  position: relative;
}
.cover :deep(h1) {
  font-size: 3.5rem;
}
</style>
