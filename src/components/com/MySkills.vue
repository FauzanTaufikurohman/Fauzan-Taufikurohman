<template>
  <section id="skills" class="skills-section py-5">
    <div class="container text-center">
      <h2 class="mb-4 text-light">Keahlian</h2>
      <p class="text-light mb-5">Kemampuan teknis yang saya kuasai</p>

      <div class="row justify-content-center">
        <div
          v-for="(skill, index) in skills"
          :key="index"
          class="col-6 col-md-4 col-lg-3 mb-4"
        >
          <div class="skill-card p-4 shadow-sm">
            <a :href="skill.href" target="_blank" class="text-decoration-none">
              <i :class="skill.icon" :style="{ color: skill.color }"></i>
            </a>
            <h5 class="mt-3 text-white">{{ skill.name }}</h5>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SkillsSection",
  data() {
    return {
      skills: [
        {
          name: "HTML",
          icon: "fab fa-html5",
          color: "#e34c26",
          href: "https://html.com/html5/",
        },
        {
          name: "CSS",
          icon: "fab fa-css3-alt",
          color: "#264de4",
          href: "https://www.w3schools.com/Css/",
        },
        {
          name: "JavaScript",
          icon: "fab fa-js",
          color: "#f0db4f",
          href: "https://www.w3schools.com/js/",
        },
        {
          name: "Vue.js",
          icon: "fab fa-vuejs",
          color: "#42b883",
          href: "https://vuejs.org/",
        },
        {
          name: "PHP",
          icon: "fab fa-php",
          color: "#777bb4",
          href: "https://www.php.net/",
        },
        {
          name: "CodeIgniter",
          icon: "fas fa-fire",
          color: "#ee4623",
          href: "https://codeigniter.com/",
        },
        {
          name: "GitHub",
          icon: "fab fa-github",
          color: "#ffffff",
          href: "https://github.com",
        },
        {
          name: "Laravel",
          icon: "fab fa-laravel",
          color: "#ff2d20",
          href: "https://laravel.com",
        },
      ],
    };
  },
};
</script>

<style scoped>
.skills-section {
  background: linear-gradient(180deg, #001f4d, #003366, #001a33);
  color: #fff;
  position: relative;
  overflow: hidden;
}

.skills-section::before {
  content: "";
  position: absolute;
  top: -20%;
  left: 0;
  width: 100%;
  height: 150%;
  background: radial-gradient(
    circle at 50% 0%,
    rgba(0, 170, 255, 0.2),
    transparent 70%
  );
  z-index: 0;
  animation: flow 8s infinite alternate ease-in-out;
}

@keyframes flow {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(30px);
  }
}

.skill-card {
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  backdrop-filter: blur(6px);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  z-index: 1;
  position: relative;
}

.skill-card i {
  font-size: 2.5rem;
  text-shadow: 0 0 10px rgba(0, 195, 255, 0.6);
}

.skill-card:hover {
  transform: scale(1.05);
  box-shadow: 0 0 15px rgba(0, 195, 255, 0.6), 0 0 30px rgba(0, 195, 255, 0.3);
}
</style>
