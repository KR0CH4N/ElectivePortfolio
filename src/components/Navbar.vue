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
let scrollListener: (() => void) | null = null

function updateNav() {
  let current = 'home'
  document.querySelectorAll<HTMLElement>('main .section, main .hero').forEach((s) => {
    if (s.getBoundingClientRect().top <= 150) current = s.id
  })
  activeId.value = current
}

function scrollToId(id: string) {
  document.querySelector<HTMLElement>('#' + id)?.scrollIntoView({ behavior: 'smooth' })
}

onMounted(() => {
  updateNav()
  scrollListener = () => updateNav()
  window.addEventListener('scroll', scrollListener)
})

onBeforeUnmount(() => {
  if (scrollListener) window.removeEventListener('scroll', scrollListener)
})
</script>

<template>
  <nav class="navbar">
    <div class="nav-inner">
      <div class="nav-logo">CW</div>
      <ul class="nav-menu">
        <li v-for="link in links" :key="link.id">
          <a
            :href="'#' + link.id"
            class="nav-link"
            :class="{ active: activeId === link.id }"
            @click.prevent="scrollToId(link.id)"
          >{{ link.label }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped></style>