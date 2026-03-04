<script setup>
import { ref } from 'vue'
const open = ref(false)
</script>

<template>
  <span @click="open = true" class="cursor-zoom-in">
    <slot />
  </span>
  <Teleport to="body">
    <div v-if="open" @click="open = false" 
      class="fixed inset-0 z-50 flex items-center justify-center bg-black/90 cursor-zoom-out p-4">
      <img v-if="$slots.default" 
        :src="$slots.default()[0]?.children?.[0]?.props?.src || $slots.default()[0]?.props?.src"
        class="max-h-[90vh] max-w-[95vw] object-contain" />
    </div>
  </Teleport>
</template>
