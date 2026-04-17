<template>
  <div class="w-full min-w-0 overflow-x-auto pb-1">
    <div class="flex gap-3">
      <button
        v-for="(src, i) in media"
        :key="i"
        @click.prevent="openLightbox(src)"
        class="flex-shrink-0 rounded-lg overflow-hidden border border-white/10 hover:border-white/30 transition-all cursor-zoom-in group relative"
        :class="media.length === 1 ? 'w-full' : 'w-44 md:w-64'"
      >
        <!-- Video -->
        <video
          v-if="isVideo(src)"
          :src="src"
          autoplay
          muted
          loop
          playsinline
          class="w-full h-36 md:h-40 object-cover object-top pointer-events-none"
        />
        <!-- Image -->
        <img
          v-else
          :src="src"
          :alt="`Screenshot ${i + 1}`"
          class="w-full h-36 md:h-40 object-cover object-top"
          loading="lazy"
        />
        <!-- Play icon overlay for videos -->
        <div v-if="isVideo(src)" class="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity bg-black/30">
          <svg class="w-10 h-10 text-white drop-shadow-lg" fill="currentColor" viewBox="0 0 24 24">
            <path d="M8 5v14l11-7z"/>
          </svg>
        </div>
      </button>
    </div>
  </div>
</template>

<script setup>
import { inject } from 'vue'

defineProps({
  media: {
    type: Array,
    default: () => []
  }
})

const openLightbox = inject('openLightbox')

function isVideo(src) {
  return /\.(mp4|webm|mov|ogg)$/i.test(src)
}
</script>
