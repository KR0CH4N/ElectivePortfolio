<script setup lang="ts">
import { inject, ref } from 'vue'

interface ProjectImage {
  src: string
  alt: string
}

interface Project {
  number: string
  name: string
  brief: string
  tag: string
  cover: string
  description: string
  details: string[]
  tech: string[]
  link?: string
  images: ProjectImage[]
}

const openLightbox = inject<(src: string) => void>('openLightbox', () => {})

const projects = ref<Project[]>([
  {
    number: '01',
    name: 'RDC Technology Solutions, Inc. — Help Desk Portal',
    brief: 'IT Support Ticketing System · Production Deployed',
    tag: 'Production',
    cover: '/images/rdcticketingsystem/landingpage.png',
    description:
      "Built and deployed a production IT support ticketing system for RDC Technology Solutions, Inc., " +
      "owned end-to-end from backend architecture to DevOps delivery. The Express.js/Node.js backend handles " +
      "technician monitoring, ticket assignment based on client requests, technician case logging, and role-based " +
      "access across 4 user roles: Admin, Client, Technician, and Helpdesk. Shipped through a full deployment " +
      "workflow: Docker containerization, Nginx reverse proxy, SSL via Certbot, PM2 process management, and a cloud VPS server.",
    details: [
      'Backend built with Express.js on top of Node.js (AI-assisted)',
      'REST-style API for tickets, users, and case logging',
      'Frontend built with native HTML, CSS, and JavaScript (AI-assisted)',
      'Role-based access control with 4 user roles: Admin, Client, Technician, Helpdesk',
      'MySQL database for ticket and user management',
      'Containerized using Docker for consistent deployment (AI-assisted)',
      'Configured Nginx as web server and reverse proxy (AI-assisted)',
      'Secured with SSL certificates via Certbot',
      'Managed process persistence using PM2',
      'Deployed and configured on a cloud VPS',
    ],
    tech: ['Node.js / Express.js', 'MySQL', 'Docker', 'Nginx', 'Certbot / SSL', 'PM2', 'Cloud VPS'],
    images: [
      { src: '/images/rdcticketingsystem/landingpage.png', alt: 'Landing Page' },
      { src: '/images/rdcticketingsystem/dashboard.png', alt: 'Dashboard' },
      { src: '/images/rdcticketingsystem/ticket.png', alt: 'Ticket View' },
    ],
  },

  {
    number: '02',
    name: 'Student Sanction Management & Email Notification System',
    brief: 'PHP · MySQL · PHPMailer · Automated Notifications',
    tag: 'Production',
    cover: '/images/sanctionsystem/sanctionview.png',
    description:
      "Developed a web-based Student Sanction Management & Email Notification System for the College of Engineering " +
      "and Architecture at Cagayan State University – Carig Campus. The system digitizes sanction records, automates donation tracking, " +
      "and provides real-time transparency reports, with automated email notifications via PHPMailer.",
    details: [
      'Built using HTML, CSS, JavaScript, PHP, and MySQL',
      'Automated email notifications via PHPMailer integrated with Gmail',
      'Digitized sanction records for faster retrieval and reduced errors',
      'Implemented transparency reporting for material donations allocation',
      'Designed responsive layouts for both desktop and mobile views',
      'Deployed online using InfinityFree hosting for real-world validation',
    ],
    tech: ['HTML / CSS / JS', 'PHP', 'MySQL', 'PHPMailer', 'InfinityFree'],
    images: [
      { src: '/images/sanctionsystem/sanctionview.png', alt: 'Sanction View' },
      { src: '/images/sanctionsystem/email.png', alt: 'Automated Email Notification' },
      { src: '/images/sanctionsystem/transactions.png', alt: 'Transactions View' },
    ],
  },
  {
    number: '03',
    name: 'Sumobot Robotics — Regional Convention 2025',
    brief: 'Arduino · Autonomous · Competition Ready',
    tag: 'Hardware',
    cover: '/images/sumobot/sumofinal.jpg',
    description:
      "Designed and developed a sumobot for the Regional Convention 2025: 9th CPE Challenge at Saint Mary's University. " +
      "Built on an Arduino Nano with a DRV8833 motor driver, three ultrasonic sensors, and a line sensor for ring-edge detection. " +
      "Programmed to autonomously detect and engage opponents while surviving in-ring.",
    details: [
      'Arduino Nano microcontroller for core logic',
      'DRV8833 motor driver controlling two DC motors',
      'Three ultrasonic sensors for front and side detection',
      'Line sensor for edge detection and ring safety',
      'Autonomous programming for opponent engagement and ring survival',
      'Designed and tested for competition readiness at Regional Convention 2025',
    ],
    tech: ['Arduino Nano', 'DRV8833', 'Ultrasonic Sensors', 'Line Sensor', 'Autonomous'],
    images: [
      { src: '/images/sumobot/sumo3d.png', alt: 'Sumo 3D Model' },
      { src: '/images/sumobot/sumofinal.jpg', alt: 'Sumo Final Design' },
      { src: '/images/sumobot/sumocompe.jpg', alt: 'Sumo Competition' },
    ],
  },
])

const activeProject = ref<number | null>(null)

function toggleProject(index: number) {
  activeProject.value = activeProject.value === index ? null : index
}
</script>

<template>
  <!-- PROJECTS -->
  <section id="projects" class="section">
    <h2 class="section-title">Projects</h2>

    <div
      v-for="(project, index) in projects"
      :key="project.number"
      class="project-card"
      :class="{ active: activeProject === index }"
      @click="toggleProject(index)"
    >
      <div class="project-cover" :style="project.cover ? { backgroundImage: `url('${project.cover}')` } : {}">
        <div class="project-cover-overlay">
          <span class="project-number">{{ project.number }}</span>
          <h3 class="project-name">{{ project.name }}</h3>
          <p class="project-brief">{{ project.brief }}</p>
          <span class="project-tag">{{ project.tag }}</span>
        </div>
      </div>
      <div class="project-drawer" @click.stop>
        <div class="project-imgs">
          <img
            v-for="img in project.images"
            :key="img.src"
            :src="img.src"
            :alt="img.alt"
            class="p-img"
            @click="openLightbox(img.src)"
          />
        </div>
        <p class="project-desc">{{ project.description }}</p>
        <ul class="project-detail-list">
          <li v-for="detail in project.details" :key="detail">{{ detail }}</li>
        </ul>
        <div class="project-tech">
          <span v-for="tech in project.tech" :key="tech">{{ tech }}</span>
        </div>
        <a v-if="project.link" class="project-repo" :href="project.link" target="_blank" rel="noopener">View on GitHub &nearr;</a>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
