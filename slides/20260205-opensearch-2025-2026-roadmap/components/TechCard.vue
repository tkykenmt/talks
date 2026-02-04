<script setup>
import { ref } from 'vue'
const props = defineProps({
  title: String,
  color: { type: String, default: 'cyan' }
})
const open = ref(false)
</script>

<template>
  <div @click="open = true" 
    class="cursor-pointer rounded-lg p-3 text-center transition hover:scale-105"
    :class="`bg-${color}-900/30 hover:bg-${color}-900/50`">
    <div class="font-bold" :class="`text-${color}-400`">{{ title }}</div>
  </div>
  <Teleport to="body">
    <div v-if="open" @click="open = false" 
      class="fixed inset-0 z-50 flex items-center justify-center bg-black/95 cursor-pointer p-4">
      <div class="bg-gray-900 rounded-2xl p-10 max-w-4xl w-full border border-gray-600" @click.stop>
        <div class="text-3xl font-bold mb-6" :class="`text-${color}-400`">{{ title }}</div>
        <div class="text-gray-100 text-xl leading-relaxed">
          <slot />
        </div>
        <div class="mt-8 text-right">
          <button @click="open = false" class="text-gray-400 hover:text-white text-lg">閉じる</button>
        </div>
      </div>
    </div>
  </Teleport>
</template>
