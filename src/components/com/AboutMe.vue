<template>
  <section id="tentang" class="container py-5 text-light">
    <div class="row align-items-center py-5 flex-column flex-md-row">
      <div
        class="col-12 col-md-5 text-center text-md-start mt-4 mt-md-0 animate__animated animate__fadeInLeft"
      >
        <img
          src="../../assets/images/Zan.jpg"
          alt="Foto HellZan"
          class="rounded-circle shadow-lg photo-animate img-fluid"
        />
      </div>

      <div
        class="col-12 col-md-7 text-center text-md-start animate__animated animate__fadeInRight mt-4 mt-md-0"
      >
        <h2 class="text-white mb-3">Tentang Saya</h2>
        <p class="lead">
          Saya adalah seorang developer web dan IoT yang senang menjelajah
          teknologi terbaru. Saya terus belajar dan berkembang untuk menciptakan
          solusi yang inovatif dan efektif.
        </p>
        <p>
          Dengan pengalaman dalam berbagai teknologi, saya berfokus pada
          pengembangan web yang dinamis serta proyek IoT yang menghubungkan
          dunia nyata dengan solusi digital.
        </p>

        <h5 class="text-white mt-4">Pengalaman</h5>
        <ul class="list-unstyled d-flex flex-column justify-content-center">
          <li class="experience-item">Pengembang web Vue.js & Laravel.</li>
          <li class="experience-item">IoT: ESP32 & Arduino.</li>
          <li class="experience-item">Database: MySQL & MongoDB</li>
        </ul>

        <h5 class="text-white mt-4">Motto Saya</h5>
        <p class="fw-small">
          "Inovasi adalah kunci untuk membuka dunia baru penuh kemungkinan."
        </p>
      </div>
    </div>
  </section>
</template>
<script setup>
import { onMounted } from "vue";

onMounted(() => {
  const aboutSection = document.getElementById("tentang");
  if (!aboutSection) return;

  const leftElement = aboutSection.querySelector(".animate__fadeInLeft");
  const rightElement = aboutSection.querySelector(".animate__fadeInRight");

  if (!leftElement || !rightElement) return;

  const observer = new IntersectionObserver(
    (entries, observer) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          leftElement.classList.add("show-animate");
          rightElement.classList.add("show-animate");
          observer.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.3 }
  );

  observer.observe(aboutSection);
});
</script>

<style scoped>
body {
  background-color: #0a1f33;
  font-family: "Poppins", sans-serif;
}

h1 {
  text-shadow: 2px 2px 5px rgba(0, 191, 255, 0.8);
}

/* Animasi hover pada item pengalaman */
.experience-item {
  transition: transform 0.3s ease, color 0.3s ease;
}

.experience-item:hover {
  color: #1e90ff;
  transform: scale(1.05);
}

.photo-animate {
  opacity: 0;
  width: 300px;
  max-width: 80vw;
  border-radius: 50%;
  border: 4px solid transparent;
  background-origin: border-box;
  background-clip: content-box;
  animation: fadeIn 2s ease-in-out forwards, glowEffect 2s infinite alternate;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

@media (max-width: 992px) {
  .photo-animate {
    width: 200px;
    max-width: 40vw;
  }
}
/* Responsive image size */
@media (max-width: 768px) {
  .photo-animate {
    width: 180px;
    max-width: 60vw;
  }
}

@media (max-width: 480px) {
  .photo-animate {
    width: 120px;
    max-width: 80vw;
  }
}

/* Animasi fadeIn untuk foto */
@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes glowEffect {
  0% {
    box-shadow: 0 0 10px 5px rgba(0, 191, 255, 0.7),
      0 0 20px rgba(0, 157, 255, 0.8);
  }
  50% {
    box-shadow: 0 0 20px 10px rgba(0, 128, 255, 0.8),
      0 0 30px rgba(0, 123, 255, 1);
  }
  100% {
    box-shadow: 0 0 10px 5px rgba(0, 225, 255, 0.7),
      0 0 20px rgba(10, 144, 255, 0.8);
  }
}

.photo-animate:hover {
  animation: glowEffect 2s ease-in-out infinite alternate;
}

.photo-animate {
  animation: fadeIn 2s ease-in-out forwards, parallax 4s infinite alternate;
}
@keyframes parallax {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-20px);
  }
}

.animate__animated {
  opacity: 0;
  animation: fadeInSection 1.5s ease-out forwards;
}

.animate__fadeInLeft {
  animation: fadeInLeft 1.5s ease-out forwards;
}

.animate__fadeInRight {
  animation: fadeInRight 1.5s ease-out forwards;
}
/* Hide default before scroll */
.animate__fadeInLeft,
.animate__fadeInRight {
  opacity: 0;
  transform: translateX(0);
}

/* Aktifkan animasi saat class 'show-animate' ditambahkan */
.animate__fadeInLeft.show-animate {
  animation: fadeInLeft 1.5s ease-out forwards;
}

.animate__fadeInRight.show-animate {
  animation: fadeInRight 1.5s ease-out forwards;
}

@keyframes fadeInSection {
  0% {
    opacity: 0;
    transform: translateY(50px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(-50px);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  0% {
    opacity: 0;
    transform: translateX(50px);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

/* Responsive text alignment and spacing */
@media (max-width: 768px) {
  .text-md-start {
    text-align: center !important;
  }
  .mt-md-0 {
    margin-top: 1rem !important;
  }
  .py-5 {
    padding-top: 2rem !important;
    padding-bottom: 2rem !important;
  }
  .container {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}

@media (max-width: 480px) {
  h2,
  h5 {
    font-size: 1.2rem;
  }
  .lead {
    font-size: 1rem;
  }
  .container {
    padding-left: 0.5rem;
    padding-right: 0.5rem;
  }
}
</style>