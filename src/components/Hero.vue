<script setup lang="ts"></script>

<template>
  <!-- HERO -->
  <section id="home" class="hero">
    <div class="hero-content">
      <div class="hero-text">
        <p class="hero-greeting">Hi, my name is</p>
        <h1 class="hero-name">Chrystvil Wong-Wong M. Baculi</h1>
        <h2 class="hero-subtitle">BS in Computer Engineering</h2>
        <p class="hero-desc">
          I am a 4th-year Computer Engineering student passionate about DevOps, infrastructure, and systems administration.
        </p>
        <p class="hero-desc">
          Welcome to my Portfolio!
        </p>
        <div class="download-cv">
          <a href="/cv/WongCV.pdf" download="WongCV.pdf" class="download-cv-button">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
              <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
              <polyline points="7 10 12 15 17 10"></polyline>
              <line x1="12" y1="15" x2="12" y2="3"></line>
            </svg>
            Download CV
          </a>
        </div>
        <div class="hero-badges">
          <span class="badge green dot">Open to Work</span>
          <span class="badge navy">Full-Stack Development</span>
          <span class="badge navy">DevOps</span>
          <span class="badge navy">Systems Administration</span>
        </div>
      </div>
      <div class="hero-photo-wrap">
        <div class="hero-photo-inner">
          <img src="/WongFormal.png" alt="Portrait" class="hero-photo" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>