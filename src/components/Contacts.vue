<script setup lang="ts"></script>

<template>
  <!-- CONTACT -->
  <section id="contact" class="section contact-section">
    <div class="contact-card">
      <header class="contact-card-header">
        <svg class="contact-header-icon" 
        viewBox="0 0 24 24" 
        fill="none" 
        stroke="currentColor" 
        stroke-width="2" 
        stroke-linecap="round" 
        stroke-linejoin="round" 
        aria-hidden="true">
          <circle cx="12" cy="12" r="10" />
          <line x1="12" y1="16" x2="12" y2="12" />
          <line x1="12" y1="8" x2="12.01" y2="8" />
        </svg>
        <h3 class="contact-card-title">Connect With Me</h3>
      </header>

      <p class="contact-card-intro">Prefer other ways to reach me? Here's how you can connect:</p>

      <ul class="contact-list">
        <li>
          <a href="mailto:baculiwong@gmail.com" class="contact-row">
            <span class="contact-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" 
              fill="none" 
              stroke="currentColor" 
              stroke-width="2" 
              stroke-linecap="round" 
              stroke-linejoin="round">
                <rect x="2" 
                      y="4" 
                      width="20" 
                      height="16" 
                      rx="2" />
                <path d="m22 7-10 6L2 7" />
              </svg>
            </span>
            <span class="contact-row-text">
              <span class="contact-row-title">Email</span>
              <span class="contact-row-value">baculiwong@gmail.com</span>
              <span class="contact-row-hint">Send me an email anytime</span>
            </span>
            <svg class="contact-chevron" 
                 viewBox="0 0 24 24" 
                 fill="none" 
                 stroke="currentColor" 
                 stroke-width="2" 
                 stroke-linecap="round" 
                 stroke-linejoin="round" 
                 aria-hidden="true">
              <path d="m9 18 6-6-6-6" />
            </svg>
          </a>
        </li>

        <li>
          <a href="https://github.com/KR0CH4N" target="_blank" rel="noopener noreferrer" class="contact-row">
            <span class="contact-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" 
                   fill="none" 
                   stroke="currentColor" 
                   stroke-width="2" 
                   stroke-linecap="round" 
                   stroke-linejoin="round">
                <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.4 5.4 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4" />
                <path d="M9 18c-4.51 2-5-2-7-2" />
              </svg>
            </span>
            <span class="contact-row-text">
              <span class="contact-row-title">GitHub</span>
              <span class="contact-row-value">github.com/KR0CH4N</span>
              <span class="contact-row-hint">See what I'm building</span>
            </span>
            <svg class="contact-chevron" viewBox="0 0 24 24" 
                fill="none" 
                stroke="currentColor" 
                stroke-width="2" 
                stroke-linecap="round" 
                stroke-linejoin="round" 
                aria-hidden="true">
              <path d="m9 18 6-6-6-6" />
            </svg>
          </a>
        </li>

        <li>
          <a href = "https://www.linkedin.com/in/chrystvil-wong-wong-m-baculi-5969482b0" target="_blank" rel="noopener noreferrer" class="contact-row">
            <span class="contact-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" 
                   fill="none" 
                   stroke="currentColor" 
                   stroke-width="2" 
                   stroke-linecap="round" 
                   stroke-linejoin="round">
                <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z" />
                <rect x="2" y="9" width="4" height="12" />
                <circle cx="4" cy="4" r="2" />
              </svg>
            </span>
            <span class="contact-row-text">
              <span class="contact-row-title">LinkedIn</span>
              <span class="contact-row-value">linkedin.com/in/chrystvil-wong-wong-m-baculi</span>
              <span class="contact-row-hint">Let's connect professionally</span>
            </span>
            <svg class="contact-chevron" viewBox="0 0 24 24" 
                 fill="none" 
                 stroke="currentColor" 
                 stroke-width="2" 
                 stroke-linecap="round" 
                 stroke-linejoin="round" 
                 aria-hidden="true">
              <path d="m9 18 6-6-6-6" />
            </svg>
          </a>
        </li>

        <li>
          <div class="contact-row contact-row-static">
            <span class="contact-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z" />
                <circle cx="12" cy="10" r="3" />
              </svg>
            </span>
            <span class="contact-row-text">
              <span class="contact-row-title">Location</span>
              <span class="contact-row-value">Burgos, Isabela, Philippines</span>
              <span class="contact-row-hint">Open to remote work</span>
            </span>
          </div>
        </li>
      </ul>

      <footer class="contact-card-footer">
        <p>
          <svg viewBox="0 0 24 24" fill="none" 
               stroke="currentColor" 
               stroke-width="2" 
               stroke-linecap="round" 
               stroke-linejoin="round" 
               aria-hidden="true">
            <circle cx="12" cy="12" r="10" />
            <polyline points="12 6 12 12 16 14" />
          </svg>
          Usually responds within 24 hours
        </p>
        <p>
          <svg viewBox="0 0 24 24" 
               fill="none" 
               stroke="currentColor" 
               stroke-width="2" 
               stroke-linecap="round" 
               stroke-linejoin="round" 
               aria-hidden="true">
            <path d="M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z" />
          </svg>
          Your information is kept private
        </p>
      </footer>
    </div>
  </section>
</template>

<style scoped></style>