<!-- Two-cols layout: Two Content -->
<script setup>
import bgDefault from '../assets/theme/bg-default.png'
</script>

<template>
  <div class="slidev-layout two-cols grid grid-cols-2 gap-4 h-full p-12" :style="{ backgroundImage: `url(${bgDefault})` }">
    <div class="col-left">
      <slot name="default" />
    </div>
    <div class="col-right">
      <slot name="right" />
    </div>
  </div>
</template>

<style scoped>
.two-cols {
  background-size: cover;
  background-position: center;
  color: white;
}
</style>
