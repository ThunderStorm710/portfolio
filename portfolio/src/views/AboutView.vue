<template>
  <div :class="['about-page', theme]">
    <Navbar :theme="theme" />

    <!-- Introduction Section -->
    <section :class="['introduction', theme]">
      <img src="@/assets/person.png" alt="Profile Picture" class="profile-pic" />
      <div class="intro-text">
        <h1>Pedro Ascensão</h1>
        <p>I'm a passionate Web Designer & Developer currently pursuing a Master's degree in Computer Engineering at the University of Coimbra. My focus lies in software development, backend services, and web applications.</p>
      </div>
    </section>

    <!-- Education Section -->
    <section :class="['education', theme]">
      <h2>Education</h2>
      <div class="education-item">
        <img src="@/assets/uc-logo.png" alt="University of Coimbra" class="edu-logo" />
        <div class="edu-details">
          <h3>Master's in Computer Engineering - Software Engineering</h3>
          <p>University of Coimbra, 2023 - Present</p>
        </div>
      </div>
      <div class="education-item">
        <img src="@/assets/uc-logo.png" alt="University of Coimbra" class="edu-logo" />
        <div class="edu-details">
          <h3>Bachelor's in Computer Engineering</h3>
          <p>University of Coimbra, 2020 - 2023</p>
          <p>Final Grade: 16</p>
        </div>
      </div>
    </section>

    <!-- Experience Section -->
    <section :class="['experience', theme]">
      <h2>Experience</h2>
      <div class="experience-item">
        <img src="@/assets/cisuc-logo.png" alt="CISUC" class="exp-logo" />
        <div class="exp-details">
          <h3>Graduate Scholarship - POWER Project</h3>
          <p>CISUC, 2023 - 2024</p>
          <p>Kubernetes cluster management, performance evaluation, and scientific publication.</p>
        </div>
      </div>
      <div class="experience-item">
        <img src="@/assets/cisuc-logo.png" alt="CISUC" class="exp-logo" />
        <div class="exp-details">
          <h3>Scientific Research Initiation Scholarship - OREOS Project</h3>
          <p>CISUC, 2022 - 2023</p>
          <p>Container orchestration, microservices, and Cloud-to-Edge environments.</p>
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section :class="['skills', theme]">
      <h2>Skills</h2>
      <div class="skills-list">
        <div class="skill-item">
          <img src="@/assets/icons/database.svg" alt="Database" />
          <p>Database Management</p>
        </div>
        <div class="skill-item">
          <img src="@/assets/icons/api.svg" alt="API" />
          <p>API Development</p>
        </div>
        <div class="skill-item">
          <img src="@/assets/icons/docker.svg" alt="Docker" />
          <p>Container Orchestration</p>
        </div>
        <div class="skill-item">
          <img src="@/assets/icons/security.svg" alt="Security" />
          <p>Security</p>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section :class="['projects', theme]">
      <h2>Projects</h2>
      <div class="project-item">
        <img src="@/assets/projects/n3e.png" alt="N3E Project" class="project-img" />
        <div class="project-details">
          <h3>N3E Website</h3>
          <p><a href="https://n3e.vercel.app" target="_blank">n3e.vercel.app</a></p>
        </div>
      </div>
      <div class="project-item">
        <img src="@/assets/projects/moelasware.png" alt="MoelasWare" class="project-img" />
        <div class="project-details">
          <h3>MoelasWare Quiz Management App</h3>
          <p><a href="https://moelasware.xyz" target="_blank">moelasware.xyz</a></p>
        </div>
      </div>
      <div class="project-item">
        <img src="@/assets/projects/clinicplus.png" alt="ClinicPlus" class="project-img" />
        <div class="project-details">
          <h3>ClinicPlus</h3>
          <p>A cloud-based service environment using AWS (2024)</p>
        </div>
      </div>
    </section>

    <!-- Honors and Awards Section -->
    <section :class="['honors', theme]">
      <h2>Honors and Awards</h2>
      <div class="honors-item">
        <img src="@/assets/icons/award.svg" alt="Merit Award" />
        <p>Top 5% Best Students at University of Coimbra (2022)</p>
      </div>
    </section>

    <!-- Contact Section -->
    <section :class="['contact', theme]">
      <h2>Contact Me</h2>
      <p>Email: <a href="mailto:pascensao77@gmail.com">pascensao77@gmail.com</a></p>
      <p>LinkedIn: <a href="https://www.linkedin.com/in/pedro-ascensao/" target="_blank">linkedin.com/in/pedro-ascensao</a></p>
    </section>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  theme: String,
});
</script>

<style scoped>
.about-page {
  padding: 20px;
}

.introduction, .education, .experience, .skills, .projects, .honors, .contact {
  margin-bottom: 40px;
  padding: 20px;
  border-radius: 10px;
  background-color: var(--bg-color);
  transition: background-color 0.5s ease, color 0.5s ease;
}

.introduction {
  display: flex;
  align-items: center;
  gap: 20px;
}

.profile-pic {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid #f0c040;
}

h1, h2 {
  color: #f0c040;
}

a {
  color: #f0c040;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

.edu-logo, .exp-logo {
  width: 60px;
  height: auto;
  margin-right: 20px;
}

.education-item, .experience-item {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.skills-list {
  display: flex;
  gap: 20px;
  justify-content: space-around;
}

.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.skill-item img {
  width: 50px;
  height: 50px;
  margin-bottom: 10px;
}

.project-item {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.project-img {
  width: 80px;
  height: auto;
  margin-right: 20px;
}

.honors-item {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.honors-item img {
  width: 50px;
  height: auto;
  margin-right: 20px;
}

.contact {
  text-align: center;
}
</style>
