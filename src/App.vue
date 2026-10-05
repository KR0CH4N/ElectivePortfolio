<script setup lang="ts">
import { onBeforeUnmount, onMounted, provide, ref } from 'vue'
import Navbar from './components/Navbar.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Hero from './components/Hero.vue'
import Contacts from './components/Contacts.vue'

// --- Lightbox ---
const lightboxOpen = ref(false)
const lightboxSrc = ref('')

function openLightbox(src: string) {
  lightboxSrc.value = src
  lightboxOpen.value = true
  document.body.style.overflow = 'hidden'
}
function closeLightbox() {
  lightboxOpen.value = false
  document.body.style.overflow = ''
}
provide('openLightbox', openLightbox)

function onKeydown(e: KeyboardEvent) {
  if (e.key === 'Escape') closeLightbox()
}

onMounted(() => window.addEventListener('keydown', onKeydown))
onBeforeUnmount(() => {
  window.removeEventListener('keydown', onKeydown)
})
</script>

<template>
  <div>
    <Navbar />
    <main>
      <Hero />
      <About />
      <Projects />
      <Contacts />
    </main>

    <footer class="footer">
      <p>Developed by Engr. Chrystvil Wong-Wong M. Baculi</p>
    </footer>

    <!-- Lightbox -->
    <div id="lightbox" class="lightbox" :class="{ show: lightboxOpen }" @click="closeLightbox">
      <span class="lightbox-close">&times;</span>
      <img id="lightbox-img" class="lightbox-img" :src="lightboxSrc" alt="" />
    </div>
  </div>
</template>

<style scoped></style>