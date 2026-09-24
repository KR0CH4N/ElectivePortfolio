<script setup lang="ts"></script>

<template>
  <!-- ABOUT -->
  <section id="about" class="section">
    <h2 class="section-title">About Me</h2>

    <p class="about-text">
      I am a detail-oriented Computer Engineering senior and certified Civil Service Professional 
      with a solid foundation in computer networking, backed by Networking Basics and 
      Networking Devices &amp; Initial Configuration certifications from the Cisco Networking Academy. 
      I combine technical proficiency in software development (Python, Django, Node.js) with hands-on experience 
      in Windows/Linux server administration and embedded systems.
    </p>
    <p class="about-text">
      As a proactive problem-solver, I enjoy taking concepts from ideation to working deployment. 
      When I am not studying or coding, I love exploring new tools, keeping up with emerging 
      technologies, and working on engineering side projects that push my technical growth.
    </p>

    <div class="skills-section">
      <h3 class="section-subtitle">Technologies &amp; Skills</h3>

      <div class="skills-category">
        <h4>Software Development</h4>
        <div class="skill-tags">
          <span>Python</span>
          <span>Java</span>
          <span>JavaScript / TypeScript</span>
          <span>HTML / CSS</span>
          <span>Vue.js</span>
          <span> Django </span>
          <span>Node.js</span>
          <span>REST APIs</span>
        </div>
      </div>

      <div class="skills-category">
        <h4>Databases</h4>
        <div class="skill-tags">
          <span>MySQL</span>
          <span>PostgreSQL</span>
          <span>SQLite</span>
        </div>
      </div>

      <div class="skills-category">
        <h4>Embedded Systems</h4>
        <div class="skill-tags">
          <span> ESP32</span>
          <span>Arduino</span>
          <span>Raspberry Pi</span>
          <span>Embedded C</span>
          <span>Microcontrollers</span>
          <span>Sensors &amp; Actuators</span>
        </div>
      </div>

      <div class="skills-category">
        <h4>Other Skills</h4>
        <div class="skill-tags">
          <span>Git / GitHub</span>
          <span>Linux</span>
          <span>Windows Server (AD DS, DNS, DHCP)</span>
          <span>Problem Solving</span>
          <span>Team Collaboration</span>
        </div>
      </div>
    </div>

    <div class="edu-section">
      <h3 class="section-subtitle">Education</h3>

      <div class="edu-timeline">
        <div class="edu-item">
          <div class="edu-dot"></div>
          <div class="edu-content">
            <div class="edu-year">2023 – Present</div>
            <h4>BS Computer Engineering</h4>
            <p>Cagayan State University – Carig Campus · College of Engineering and Architecture</p>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-dot"></div>
          <div class="edu-content">
            <div class="edu-year">2021 – 2023</div>
            <h4>Aurora Senior High School</h4>
            <p>STEM Strand · Graduated with High Honors</p>
            <ul class="edu-achievements">
              <li>Outstanding Performer in Work Immersion (Capstone)</li>
              <li>Outstanding Performer in Communication Arts</li>
            </ul>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-dot"></div>
          <div class="edu-content">
            <div class="edu-year">2019 – 2021</div>
            <h4>Burgos National High School</h4>
            <p>Graduated with High Honors</p>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-dot"></div>
          <div class="edu-content">
            <div class="edu-year">2013 – 2019</div>
            <h4>Burgos Central School</h4>
            <p>Graduated with Honors</p>
          </div>
        </div>
      </div>
    </div>

    <div class="cert-section">
      <h3 class="section-subtitle">Certifications &amp; Licenses</h3>

      <div class="cert-grid">
        <a
          class="cert-card"
          href="https://www.credly.com/badges/cb5709fe-c0eb-45e7-809f-ef8c6968be99"
          target="_blank"
          rel="noopener"
        >
          <div class="cert-head">
            <img class="cert-badge" src="/certs/networkbasicscisco.png" alt="Networking Basics Credly badge" />
            <div class="cert-body">
              <h4>Networking Basics</h4>
              <p>Cisco Networking Academy</p>
            </div>
          </div>
          <span class="cert-link">Verify on Credly &nearr;</span>
        </a>

        <a
          class="cert-card"
          href="https://www.credly.com/badges/36dc88a2-7ee6-4e8d-b7f6-3c0537f3bddf"
          target="_blank"
          rel="noopener"
        >
          <div class="cert-head">
            <img class="cert-badge" src="/certs/networkdevicescisco.png" alt="Networking Devices &amp; Initial Configuration Credly badge" />
            <div class="cert-body">
              <h4>Networking Devices &amp; Initial Configuration</h4>
              <p>Cisco Networking Academy</p>
            </div>
          </div>
          <span class="cert-link">Verify on Credly &nearr;</span>
        </a>

        <div class="cert-card">
          <div class="cert-head">
            <span class="cert-check">✔</span>
            <div class="cert-body">
              <h4>Civil Service Eligibility</h4>
              <p>Civil Service Professional Examination — Passer</p>
            </div>
          </div>
          <span class="cert-year">Issued May 2026</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>