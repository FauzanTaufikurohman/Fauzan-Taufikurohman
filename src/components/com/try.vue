<template>
  <section id="home" class="container mt-5 py-5 text-light">
    <div class="row align-items-center py-5 d-flex flex-md-row">
      <!-- Kolom Kiri: Deskripsi -->
      <div class="col-12 col-md-8 animate__animated animate__fadeInLeft">
        <h1 class="text-white text-start mb-3">FAUZAN TAUFIKUROHMAN</h1>
        <p class="lead">
          Active student of Information Technology Study Program at Brawijaya
          University with experience in Front End and Back End Development.
        </p>
      </div>

      <!-- Kolom Kanan: Foto -->
      <div
        class="col-12 col-md-3 text-center mt-4 mt-md-0 animate__animated animate__fadeInRight"
      >
        <img
          src="../../assets/images/Zan.jpg"
          alt="Foto HellZan"
          class="rounded-circle shadow-lg photo-animate"
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Portfolio",
};
</script>

<style scoped>
body {
  background-color: #0a1f33;
  font-family: "Poppins", sans-serif;
}

h1 {
  text-shadow: 2px 2px 5px rgba(0, 191, 255, 0.8);
}

.social-icons a:hover {
  color: #00bfff;
  transform: scale(1.1);
  transition: all 0.3s ease;
}

.skill-item {
  transition: transform 0.3s ease, color 0.3s ease;
}

.skill-item:hover {
  color: #1e90ff;
  transform: scale(1.05);
}
.social-icons a {
  color: #fff;
  transition: transform 0.3s ease, color 0.3s ease;
}

.github-icon:hover i {
  color: #00bcd4;
  transform: scale(1.2);
}

.linkedin-icon:hover i {
  color: #0077b5;
  transform: scale(1.2);
}

.instagram-icon:hover i {
  color: #1fa2ff;
  transform: scale(1.2);
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
}
@media (max-width: 991.98px) {
  .photo-animate {
    width: 220px;
    margin-top: 2rem;
  }
  .row.align-items-center {
    flex-direction: column !important;
  }
}

@media (max-width: 767.98px) {
  .photo-animate {
    width: 160px;
    margin-top: 1.5rem;
  }
  .col-md-8,
  .col-md-3 {
    text-align: center !important;
  }
}

@media (max-width: 575.98px) {
  .photo-animate {
    width: 120px;
    margin-top: 1rem;
  }
  h1 {
    font-size: 1.5rem;
  }
  .lead {
    font-size: 1rem;
    text-align: start;
  }
  .btn {
    font-size: 0.9rem;
    padding: 0.5rem 1rem;
  }
}

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

@keyframes parallax {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-20px);
  }
}

.photo-animate {
  animation: fadeIn 2s ease-in-out forwards, parallax 4s infinite alternate;
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