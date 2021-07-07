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
          <!-- <button type="button" class="btn-close" @click="closeModal" data-dismiss="modal" aria-label="close"></button> -->
        </div>
        <div class="modal-body">
          <div id="imgCarousel" class="carousel slide" data-bs-ride="carousel">
            <div class="carousel-inner">
              <template v-for="(item, index) in gallery" :key="item">
                <div class="carousel-item active" v-if="index === 0">
                  <img :src="require(`@/assets/img/${item}`)" class="d-block w-100" alt="...">
                </div>
                <div class="carousel-item" v-else>
                  <img :src="require(`@/assets/img/${item}`)" class="d-block w-100" alt="...">
                </div>
              </template>
              <!-- <div class="carousel-item">
                <img :src="require(`@/assets/img/${gallery}`)" class="d-block w-100" alt="...">
              </div>
              <div class="carousel-item">
                <img :src="require(`@/assets/img/${gallery}`)" class="d-block w-100" alt="...">
              </div> -->
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
            <p>Dibuat pada tahun <strong>{{ projMade }}</strong></p>
            <p>Mata kuliah : <strong>{{ lecture }}</strong></p>
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
        link: '',
        projMade: '2019 (Semester 3)',
        mainImage: 'pabw/homepage.png',
        gallery: ['pabw/daftarlaporan.png', 'pabw/input laporan.png', 'pabw/tentang.png'],
        lecture: 'Pengembangan Aplikasi Berbasis Web'
      },
      {
        id: 2,
        title: 'EzTourism',
        category: 'Web Development',
        desc: 'adalah platform yang menyediakan jasa pemesanan oleh-oleh khas Jogja dan menyediakan pelayanan jasa sewa tour guide wisata bagi para wisatawan yang hendak berkeliling menikmati keindahan “kota gudeg” ini untuk meminimalisir kendala kebutuhan dalam berwisata',
        link: '',
        projMade: '2020 (Semester 4)',
        mainImage: 'pabw/daftarlaporan.png',
        gallery: ['pabw/daftarlaporan.png', 'pabw/input laporan.png', 'pabw/tentang.png'],
        lecture: 'Pengembangan Sistem Informasi'
      },
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
      // carousel_item.forEach((item, index) => {
      //   while(index > 0) {
      //     item.classList.remove('.active')
      //   }
      // })
    },
    closeModal() {
      this.showModal = !this.showModal
    }
  }
}
</script>