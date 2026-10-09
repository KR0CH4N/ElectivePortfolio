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
  tech: string[]
  link?: string
  images: ProjectImage[]
}

const openLightbox = inject<(src: string) => void>('openLightbox', () => {})

const projects = ref<Project[]>([
  {
    number: '01',
    name: 'Thermal FPV Drone System',
    brief: 'Raspberry Pi + ESP32 · Live Thermal/RGB Feeds',
    tag: 'Hardware',
    cover: './images/thermaldrone/dronepic1.png',
    description:
      "A Raspberry Pi + ESP32 drone system that streams live thermal and RGB camera feeds over MJPEG " +
      "and relays flight-controller telemetry (GPS, battery, altitude) to a React Native mobile app client. The Raspberry Pi " +
      "runs a Flask server built around an AMG8833 8×8 thermal sensor and a Pi Camera Module (Picamera2), while " +
      "a separate ESP32 runs the flight controller and pushes JSON telemetry over a wired UART link " +
      "that the Pi relays over HTTP.",
    tech: ['Raspberry Pi', 'Flask', 'Python', 'AMG8833', 'Picamera2', 'OpenCV', 'ESP32 / Arduino', 'MPU6050', 'TinyGPS++', 'UART', 'PID Control'],
    images: [
      { src: './images/thermaldrone/dronepic1.png', alt: 'Thermal Drone' },
      { src: './images/thermaldrone/finalsetup.png', alt: 'Final System Setup' },
      { src: './images/thermaldrone/telemetryandsystemconfiguration.png', alt: 'Telemetry & System Configuration' },
    ],
  },

  {
    number: '02',
    name: 'Smart Bin Waste Sorting System',
    brief: 'Raspberry Pi 3B · TensorFlow Lite · Paper/Plastic Sorting',
    tag: 'IoT',
    cover: './images/smartwastebin/wastebinfull.png',
    description:
      "An automated paper/plastic waste sorting system for the Raspberry Pi 3B. It is not a full prototype rather it is only the core system and functionality implemented. It continuously captures camera " +
      "frames, detects objects via background subtraction, and classifies them as Paper or Plastic using a " +
      "TensorFlow Lite model (ai-edge-litert). A servo routes each item into the correct bin, an I2C LCD relays " +
      "status (including FULL! once a bin fills up), and ultrasonic sensors pause sorting when a bin is full.",
    tech: ['Raspberry Pi 3B', 'Python', 'TensorFlow Lite', 'OpenCV', 'NumPy', 'I2C LCD', 'Servo', 'HC-SR04'],
    images: [
      { src: './images/smartwastebin/wastebinmain.png', alt: 'Waste Bin System' },
      { src: './images/smartwastebin/datasetwastebin.png', alt: 'Training Dataset Samples' },
      { src: './images/smartwastebin/wastebinfull.png', alt: 'Bin Full Detection' },
    ],
  },

  {
    number: '03',
    name: 'RDC Technology Solutions, Inc. — Help Desk Portal',
    brief: 'IT Support Ticketing System · Production Deployed',
    tag: 'Production',
    cover: './images/rdcticketingsystem/landingpage.png',
    description:
      "Built and deployed a production IT support ticketing system for RDC Technology Solutions, Inc., " +
      "owned end-to-end from backend architecture to DevOps delivery. The Express.js/Node.js backend handles " +
      "technician monitoring, ticket assignment based on client requests, technician case logging, and role-based " +
      "access across 4 user roles: Admin, Client, Technician, and Helpdesk. Shipped through a full deployment " +
      "workflow: Docker containerization, Nginx reverse proxy, SSL via Certbot, PM2 process management, and a cloud VPS server.",
    tech: ['Node.js / Express.js', 'MySQL', 'Docker', 'Nginx', 'Certbot / SSL', 'PM2', 'Cloud VPS'],
    images: [
      { src: './images/rdcticketingsystem/landingpage.png', alt: 'Landing Page' },
      { src: './images/rdcticketingsystem/dashboard.png', alt: 'Dashboard' },
      { src: './images/rdcticketingsystem/ticket.png', alt: 'Ticket View' },
    ],
  },

  {
    number: '04',
    name: 'Student Sanction Management & Email Notification System',
    brief: 'PHP · MySQL · PHPMailer · Automated Notifications',
    tag: 'Production',
    cover: './images/sanctionsystem/sanctionview.png',
    description:
      "Developed a web-based Student Sanction Management & Email Notification System for the College of Engineering " +
      "and Architecture at Cagayan State University – Carig Campus. The system digitizes sanction records, automates donation tracking, " +
      "and provides real-time transparency reports, with automated email notifications via PHPMailer.",
    tech: ['HTML / CSS / JS', 'PHP', 'MySQL', 'PHPMailer', 'InfinityFree'],
    images: [
      { src: './images/sanctionsystem/sanctionview.png', alt: 'Sanction View' },
      { src: './images/sanctionsystem/email.png', alt: 'Automated Email Notification' },
      { src: './images/sanctionsystem/transactions.png', alt: 'Transactions View' },
    ],
  },
  {
    number: '05',
    name: 'Sumobot Robotics — Regional Convention 2025',
    brief: 'Arduino · Autonomous · Competition Ready',
    tag: 'Hardware',
    cover: './images/sumobot/sumofinal.jpg',
    description:
      "Designed and developed a sumobot for the Regional Convention 2025: 9th CPE Challenge at Saint Mary's University. " +
      "Built on an Arduino Nano with a DRV8833 motor driver, three ultrasonic sensors, and a line sensor for ring-edge detection. " +
      "Programmed to autonomously detect and engage opponents while surviving in-ring.",
    tech: ['Arduino Nano', 'DRV8833', 'Ultrasonic Sensors', 'Line Sensor', 'Autonomous'],
    images: [
      { src: './images/sumobot/sumo3d.png', alt: 'Sumo 3D Model' },
      { src: './images/sumobot/sumofinal.jpg', alt: 'Sumo Final Design' },
      { src: './images/sumobot/sumocompe.jpg', alt: 'Sumo Competition' },
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
        <div class="project-tech">
          <span v-for="tech in project.tech" :key="tech">{{ tech }}</span>
        </div>
        <a v-if="project.link" class="project-repo" :href="project.link" target="_blank" rel="noopener">View on GitHub &nearr;</a>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
