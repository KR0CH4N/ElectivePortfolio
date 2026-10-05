<script setup lang="ts">
const icon = (name: string) => `/skills/${name}.svg`
const local = (file: string) => `/skills/${file}`

const skillCards = [
  {
    title: 'DevOps & CI/CD',
    summary: 'GitHub Actions, Docker, Ansible, Git / GitHub',
    iconPath: 'M23 4v6h-6M1 20v-6h6M3.51 9a9 9 0 0 1 14.85-3.36L23 10M1 14l4.64 4.36A9 9 0 0 0 20.49 15',
    logos: [
      { name: 'Git', src: icon('git') },
      { name: 'GitHub', src: icon('github'), light: true },
      { name: 'GitHub Actions', src: local('github-actions.png') },
      { name: 'Docker', src: local('docker.png') },
      { name: 'Ansible', src: local('ansible.png') },
    ],
  },
  {
    title: 'Systems & Networking',
    summary: 'Linux (Ubuntu Server), Windows Server, Nginx, Cisco networking',
    iconPath: 'M4 4h16a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2zM4 14h16a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2v-2a2 2 0 0 1 2-2zM6 7h.01M6 17h.01',
    logos: [
      { name: 'Ubuntu Server', src: local('ubuntu.png') },
      { name: 'Windows Server', src: local('windows-server.png') },
      { name: 'Nginx', src: local('nginx.png') },
    ],
  },
  {
    title: 'Software Development',
    summary: 'Python, JavaScript / TypeScript, HTML / CSS, Vue.js, Django, Node.js, Django REST Framework',
    iconPath: 'M8 9l-4 3 4 3M16 9l4 3-4 3M13.5 6l-3 12',
    logos: [
      { name: 'Python', src: icon('python') },
      { name: 'JavaScript', src: icon('javascript') },
      { name: 'TypeScript', src: icon('typescript') },
      { name: 'HTML5', src: icon('html5') },
      { name: 'CSS3', src: icon('css3') },
      { name: 'Vue.js', src: icon('vuejs') },
      { name: 'Django', src: icon('django'), light: true },
      { name: 'Node.js', src: icon('nodejs') },
      { name: 'Django REST Framework', src: local('drf.png') },
    ],
  },
  {
    title: 'Databases',
    summary: 'MySQL, PostgreSQL, SQLite',
    iconPath: 'M4 6c0-1.7 3.6-3 8-3s8 1.3 8 3-3.6 3-8 3-8-1.3-8-3zM4 6v12c0 1.7 3.6 3 8 3s8-1.3 8-3V6M4 12c0 1.7 3.6 3 8 3s8-1.3 8-3',
    logos: [
      { name: 'MySQL', src: icon('mysql') },
      { name: 'PostgreSQL', src: icon('postgresql') },
      { name: 'SQLite', src: icon('sqlite') },
    ],
  },
  {
    title: 'Embedded Systems',
    summary: 'ESP32, Arduino, Raspberry Pi, Embedded C, Microcontrollers, Sensors & Actuators',
    iconPath: 'M7 7h10v10H7zM9 3v4M15 3v4M9 17v4M15 17v4M3 9h4M3 15h4M17 9h4M17 15h4',
    logos: [
      { name: 'ESP32', src: local('esp32.png') },
      { name: 'Arduino', src: icon('arduino') },
      { name: 'Arduino IDE', src: local('arduino-ide.png') },
      { name: 'Raspberry Pi', src: icon('raspberrypi') },
    ],
  },
]
</script>

<template>
  <!-- ABOUT -->
  <section id="about" class="section">
    <h2 class="section-title">About Me</h2>

    <p class="about-text">
      I'm a Computer Engineering senior and Civil Service Professional focused on DevOps and
      infrastructure, with a networking foundation backed by Cisco Networking Academy
      certifications such as Networking Basics and Networking Devices &amp; Initial Configuration.
      I set up and automate Linux and Windows server environments, work with networking,
      containers, and CI/CD pipelines. I also write backend code in Python using
      Django, and Node.js that runs on them, combined with frontend development using Vue.js, HTML, and CSS.
    </p>

    <p class="about-text">
      Aside from the software side of tech, I also have hands-on experience in Embedded Systems and Design. I have
      competed in the Robotics Competition during the Regional Convention 2025: 9th CPE Challenge at Saint Mary's University in Bayombong, Nueva Vizcaya, 
      particularly the Sumobot event. I also worked on multiple commission projects for clients, which includes 
      the main system of a Smart Waste Bin for Plastic and Paper Detection using Computer Vision, and a full prototype of a Thermal Search and Navigation Drone System.
    </p>
    <p class="about-text">
      As a proactive problem-solver, I enjoy taking concepts from ideation to working deployment.
      When I am not studying or coding, I love exploring new tools, keeping up with emerging
      technologies, and working on engineering side projects that push my technical growth.
    </p>

    <div class="skills-section">
      <h3 class="section-subtitle">Technologies &amp; Skills</h3>

      <div class="skill-cards">
        <article v-for="card in skillCards" :key="card.title" class="skill-card">
          <svg class="skill-card-icon" viewBox="0 0 24 24" fill="none"
               stroke="currentColor" stroke-width="1.8"
               stroke-linecap="round" stroke-linejoin="round">
            <path :d="card.iconPath" />
          </svg>

          <h4>{{ card.title }}</h4>
          <p class="skill-card-summary">{{ card.summary }}</p>

          <div class="skill-logos">
            <img
              v-for="logo in card.logos"
              :key="logo.name"
              :src="logo.src"
              :alt="logo.name"
              :title="logo.name"
              :class="{ light: logo.light }"
              loading="lazy"
            />
          </div>
        </article>
      </div>
    </div>

  </section>

  <!-- EDUCATION -->
  <section id="education" class="section">
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