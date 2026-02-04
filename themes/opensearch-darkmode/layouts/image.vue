<!-- Image layout -->
<script setup>
import bgImage from '../assets/theme/bg-image.png'

defineProps({
  image: String,
})
</script>

<template>
  <div class="slidev-layout image h-full" :style="{ backgroundImage: image ? `url(${image})` : `url(${bgImage})` }">
    <slot />
  </div>
</template>

<style scoped>
.image {
  background-size: cover;
  background-position: center;
  color: white;
}
</style>
