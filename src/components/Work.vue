<template>
  <div id="work" class="collapse" data-bs-parent="#accordion">
    <div class="card card-body bg-warning text-white p-5">
      <h2>My project showcase</h2>
    </div>

    <div class="card card-body p-5">
      <h3 class="mb-5">Web Development</h3>
      <div class="row">
        <div class="col-md-4 col-sm-12 my-2" v-for="project in projects" :key="project.id">
          <Showcase :project="project" @toggle-modal="toggleModal(project)"/>
        </div>
      </div>
    </div>
  </div>

  <div v-show="showModal" class="modal fade" id="cardModal" aria-hidden="true" >
    <div class="modal-dialog modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="cardModal"><strong>{{ title }}</strong></h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <div id="imgCarousel" class="carousel slide" data-bs-ride="carousel">
            <div class="carousel-inner">
              <template v-for="(item, index) in gallery" :key="item">
                <div class="carousel-item active" data-bs-interval="3000" v-if="index === 0">
                  <img :src="require(`@/assets/img/${item}`)" class="d-block w-100" alt="...">
                </div>
                <div class="carousel-item" data-bs-interval="3000" v-else>
                  <img :src="require(`@/assets/img/${item}`)" class="d-block w-100" alt="...">
                </div>
              </template>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#imgCarousel" data-bs-slide="prev">
              <span class="carousel-control-prev-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Previous</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#imgCarousel" data-bs-slide="next">
              <span class="carousel-control-next-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Next</span>
            </button>
          </div>
        </div>
        <div class="modal-footer">
          <div>
            <p style="text-align: justify;">
              <strong>{{ title }}</strong> {{ desc }}
            </p>
            <p>Made in <strong>{{ projMade }}</strong></p>
            <p>Subject course : <strong>{{ lecture }}</strong></p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Showcase from './work/Showcase.vue'

// const carousel_item = document.querySelectorAll('.carousel-item');

export default {
  name: 'Work',
  components: {
    Showcase
  },
  data() {
    return {
      projects: [],
      title: '',
      desc: '',
      projMade: '',
      gallery: () => [],
      lecture: '',
      showModal: false
    }
  },
  created() {
    this.projects = [
      {
        id: 1,
        title: 'JagaJogja',
        category: 'Web Development',
        desc: 'adalah portal laporan keamanan, kebersihan, dan fasilitas umum untuk mewujudkan Jogja Smart city.',
        link: 'https://www.google.com/',
        projMade: '2019 (Semester 3)',
        mainImage: 'pabw/homepage.png',
        gallery: ['pabw/daftarlaporan.png', 'pabw/input laporan.png', 'pabw/tentang.png'],
        lecture: 'Pengembangan Aplikasi Berbasis Web'
      },
      {
        id: 2,
        title: 'EzTourism',
        category: 'Web Development',
        desc: 'adalah platform jasa pemesanan oleh-oleh khas Jogja dan menyediakan pelayanan jasa sewa tour guide wisata bagi para wisatawan yang hendak berkeliling menikmati keindahan “kota gudeg” ini untuk meminimalisir kendala kebutuhan dalam berwisata.',
        link: 'https://www.google.com/',
        projMade: '2020 (Semester 4)',
        mainImage: 'psi/ez1.png',
        gallery: ['psi/ez1.png', 'psi/ez2.png', 'psi/ez3.png'],
        lecture: 'Pengembangan Sistem Informasi'
      },
      {
        id: 3,
        title: 'Dojo Blog',
        category: 'Web Development',
        desc: 'A simple CRD (CREATE - READ - DELETE) blog web apps built using ReactJS, a ReactJS tutorial by Net Ninja (Shaun Pelling)',
        link: 'https://dojo-blog-react.vercel.app/',
        projMade: 'March 2021',
        mainImage: 'pabw/daftarlaporan.png',
        gallery: ['pabw/daftarlaporan.png', 'pabw/input laporan.png', 'pabw/tentang.png'],
        lecture: 'React JS Tutorial by Net Ninja (Shaun Pelling)'
      },
      {
        id: 3,
        title: 'Dojo Blog',
        category: 'Web Development',
        desc: 'A simple CRD (CREATE - READ - DELETE) blog web apps built using ReactJS, a ReactJS tutorial by Net Ninja (Shaun Pelling)',
        link: 'https://dojo-blog-react.vercel.app/',
        projMade: 'March 2021',
        mainImage: 'pabw/daftarlaporan.png',
        gallery: ['pabw/daftarlaporan.png', 'pabw/input laporan.png', 'pabw/tentang.png'],
        lecture: 'React JS Tutorial by Net Ninja (Shaun Pelling)'
      }
    ]
  }, 
  methods: {
    toggleModal(project) {
      this.showModal = !this.showModal;
      this.title = project.title;
      this.desc = project.desc;
      this.projMade = project.projMade;
      this.gallery = project.gallery;
      this.lecture = project.lecture;
    },
    closeModal() {
      this.showModal = !this.showModal
    }
  }
}
</script>