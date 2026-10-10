<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'

const links = [
  { id: 'home', label: 'Home' },
  { id: 'about', label: 'About' },
  { id: 'education', label: 'Qualifications'},
  { id: 'projects', label: 'Projects' },
  { id: 'contact', label: 'Contact' },
]

const activeId = ref('home')
const menuOpen = ref(false)
let scrollListener: (() => void) | null = null
let resizeListener: (() => void) | null = null

function updateNav() {
  let current = 'home'
  document.querySelectorAll<HTMLElement>('main .section, main .hero').forEach((s) => {
    if (s.getBoundingClientRect().top <= 150) current = s.id
  })
  activeId.value = current
}

function scrollToId(id: string) {
  menuOpen.value = false
  document.querySelector<HTMLElement>('#' + id)?.scrollIntoView({ behavior: 'smooth' })
}

function onKeydown(e: KeyboardEvent) {
  if (e.key === 'Escape') menuOpen.value = false
}

function closeOnDesktop() {
  if (window.innerWidth > 768) menuOpen.value = false
}

onMounted(() => {
  updateNav()
  scrollListener = () => updateNav()
  window.addEventListener('scroll', scrollListener)
  resizeListener = closeOnDesktop
  window.addEventListener('resize', resizeListener)
  window.addEventListener('keydown', onKeydown)
})

onBeforeUnmount(() => {
  if (scrollListener) window.removeEventListener('scroll', scrollListener)
  if (resizeListener) window.removeEventListener('resize', resizeListener)
  window.removeEventListener('keydown', onKeydown)
})
</script>

<template>
  <nav class="navbar">
    <div class="nav-inner">
      <div class="nav-logo">CW</div>
      <ul id="nav-menu" class="nav-menu" :class="{ open: menuOpen }">
        <li v-for="link in links" :key="link.id">
          <a
            :href="'#' + link.id"
            class="nav-link"
            :class="{ active: activeId === link.id }"
            @click.prevent="scrollToId(link.id)"
          >{{ link.label }}</a>
        </li>
      </ul>
      <button
        class="nav-toggle"
        :class="{ open: menuOpen }"
        aria-label="Toggle navigation menu"
        :aria-expanded="menuOpen"
        aria-controls="nav-menu"
        @click="menuOpen = !menuOpen"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
  </nav>
</template>

<style scoped></style>