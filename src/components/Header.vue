<template>
  <header id="main-header">
    <div class="row g-0">
      <div class="col-lg-4 col-md 5">
        <img src="../assets/img/reza-cropped.jpg" class="foto" alt="foto reza">
      </div>

      <div class="col-lg-8 col-md-7" style="height: 100%">
        <div class="d-flex flex-column">
          <div class="p-5 bg-dark text-white">
            <div class="d-flex flex-column justify-content-start">
              <h1 class="display-4">Mohammad Reza Ali F</h1>
              <div class="social-media mt-3">
                <a href="https://www.instagram.com/mhmmdrezalif/" target="_blank" class="text-white me-4">
                  <i class="fab fa-instagram fa-2x"></i>
                </a>
                <a href="https://github.com/firdausreza" target="_blank" class="text-white me-4">
                  <i class="fab fa-github fa-2x"></i>
                </a>
                <a href="https://www.linkedin.com/in/reza-firdaus-025603202/" target="_blank" class="text-white me-4">
                  <i class="fab fa-linkedin-in fa-2x"></i>
                </a>
              </div>
            </div>
          </div>

          <div class="p-5 bg-black">
            Interested in Front End Web Development (2+ Years)
          </div>

          <div>
            <div class="d-flex flex-row text-white align-items-stretch text-center">
              <div id="home-btn" class="port-item p-4 bg-primary" data-bs-toggle="collapse" href="#home" role="button" aria-expanded="true" aria-controls="#home">
                <i class="fas fa-user-circle fa-2x"></i>
                <span class="d-none d-sm-block">Personality</span>
              </div>
              <div id="edu-btn" class="port-item p-4 bg-success" data-bs-toggle="collapse" href="#career" role="button" aria-expanded="false" aria-controls="#career">
                <i class="fas fa-graduation-cap fa-2x"></i>
                <span class="d-none d-sm-block">Career</span>
              </div>
              <div id="work-btn" class="port-item p-4 bg-warning" data-bs-toggle="collapse" href="#work" role="button" aria-expanded="false" aria-controls="#work">
                <i class="fas fa-folder-open fa-2x"></i>
                <span class="d-none d-sm-block">My Works</span>
              </div>
              <div id="contact-btn" class="port-item p-4 bg-danger" data-bs-toggle="collapse" href="#contact" role="button" aria-expanded="false" aria-controls="#contact">
                <i class="fas fa-envelope fa-2x"></i>
                <span class="d-none d-sm-block">Contact</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>