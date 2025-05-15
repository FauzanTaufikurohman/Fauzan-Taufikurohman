<template>
  <div class="container">
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top shadow px-5">
      <a class="navbar-brand text-light" href="#">My Portofolio</a>
      <ul class="navbar-nav ms-auto mb-2 mb-lg-0 d-flex flex-row gap-3">
        <li class="nav-item">
          <a class="nav-link" href="#home">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#tentang">Tentang</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#skills">Keahlian</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#project">Proyek</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#kontak">Kontak</a>
        </li>
      </ul>
    </nav>
  </div>
</template>
  
<script>
export default {
  mounted() {
    const sections = document.querySelectorAll("section");
    const navLinks = document.querySelectorAll(".nav-link");

    const onScroll = () => {
      let current = "";

      sections.forEach((section) => {
        const sectionTop = section.offsetTop - 120; // offset untuk navbar tinggi
        const sectionHeight = section.offsetHeight;
        if (
          window.scrollY >= sectionTop &&
          window.scrollY < sectionTop + sectionHeight
        ) {
          current = section.getAttribute("id");
        }
      });

      navLinks.forEach((link) => {
        link.classList.remove("active");
        const href = link.getAttribute("href");
        if (href === `#${current}`) {
          link.classList.add("active");
        }
      });
    };

    window.addEventListener("scroll", onScroll);

    // Jalankan sekali saat mounted
    onScroll();
  }
};
</script>

  
  <style scoped>
.nav-link.active {
  color: #0044ff !important; 
  transform: scale(1.1);
}

.navbar {
  background: linear-gradient(
    to right,
    #000287,
    #333333
  ); /* Gradien merah ke hitam */
  border-radius: 999px;
  border: 1px solid #140087;
  margin-top: 20px;
  margin-left: 20px;
  margin-right: 20px;
  padding: 12px 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.6);
  animation: glowing-border 2s infinite alternate; /* Animasi cahaya menyebar */
}

/* Efek cahaya yang menyebar */
@keyframes glowing-border {
  0% {
    border: 1px solid #001f87;
    box-shadow: 0 0 5px #1500ff, 0 0 10px #1e00ff, 0 0 15px #3300ff;
  }
  50% {
    border: 1px solid #370780;
    box-shadow: 0 0 10px #3700ff, 0 0 30px #000dff, 0 0 50px #001aff;
  }
  100% {
    border: 1px solid #000487;
    box-shadow: 0 0 5px #0022ff, 0 0 10px #0800ff, 0 0 15px #2600ff;
  }
}

.nav-link {
  color: white;
  font-weight: bold;
  transition: all 0.3s ease;
}

.nav-link:hover {
  color: #001aff !important;
  transform: scale(1.1);
}

.navbar-nav {
  gap: 20px;
}
</style>
  