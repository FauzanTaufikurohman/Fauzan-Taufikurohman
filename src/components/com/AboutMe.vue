<template>
  <section id="tentang" class="container mt-5 py-5 text-light">
    <div class="row align-items-center py-5">
      <div
        class="col-md-4 text-start mt-4 mt-md-0 animate__animated animate__fadeInLeft"
      >
        <img
          src="../../assets/images/Zan.jpg"
          alt="Foto HellZan"
          class="rounded-circle shadow-lg photo-animate"
        />
      </div>

      <div
        class="col-md-8 text-center text-md-start animate__animated animate__fadeInRight"
      >
        <h2 class="text-white mb-3">👨‍💻 Tentang Saya</h2>
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

        <h5 class="text-white mt-4">🔧 Pengalaman</h5>
        <ul class="list-unstyled">
          <li class="experience-item">
            • Membangun aplikasi web menggunakan Vue.js dan Laravel.
          </li>
          <li class="experience-item">
            • Mengembangkan proyek IoT berbasis ESP32 dan Arduino.
          </li>
          <li class="experience-item">
            • Berpengalaman dalam menggunakan database seperti MySQL dan
            MongoDB.
          </li>
        </ul>

        <h5 class="text-white mt-4">🌟 Motto Saya</h5>
        <p class="lead">
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
  border-radius: 50%;
  border: 4px solid transparent;
  background-origin: border-box;
  background-clip: content-box;
  animation: fadeIn 2s ease-in-out forwards, glowEffect 2s infinite alternate;
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
</style>
  