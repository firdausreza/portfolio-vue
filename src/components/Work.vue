<template>
  <div id="work" class="collapse" data-bs-parent="#accordion">
    <div class="card card-body bg-warning text-white p-5">
      <h2>My project showcase</h2>
    </div>

    <div class="card card-body p-5">
      <div class="row mb-3">
        <CategoryLabel @toggle-category="toggleCategory" catName="All" :total="allCounter" />
        <CategoryLabel @toggle-category="toggleCategory" catName="Web Development" :total="webCounter" />
        <CategoryLabel @toggle-category="toggleCategory" catName="Mobile Apps Development" :total="mobileCounter" />
        <CategoryLabel @toggle-category="toggleCategory" catName="Game Development" :total="gameCounter" />
      </div>
      <div class="row">
        <template v-if="projCategory === 'Web Development'">
          <div class="col-lg-4 col-md-6 col-sm-12 my-2" v-for="project in projCatArr" :key="project.id">
            <Showcase :project="project" @toggle-modal="toggleModal(project)"/>
          </div>
        </template>
        <template v-else-if="projCategory === 'Mobile Apps Development'">
          <div class="col-lg-4 col-md-6 col-sm-12 my-2" v-for="project in projCatArr" :key="project.id">
            <Showcase :project="project" @toggle-modal="toggleModal(project)"/>
          </div>
        </template>
        <template v-else-if="projCategory === 'Game Development'">
          <div class="col-lg-4 col-md-6 col-sm-12 my-2" v-for="project in projCatArr" :key="project.id">
            <Showcase :project="project" @toggle-modal="toggleModal(project)"/>
          </div>
        </template>
        <template v-else-if="projCategory === 'All'">
          <div class="col-lg-4 col-md-6 col-sm-12 my-2" v-for="project in projects" :key="project.id">
            <Showcase :project="project" @toggle-modal="toggleModal(project)"/>
          </div>
        </template>
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
          <div class="w-100">
            <p style="text-align: justify;">
              <strong>{{ title }}</strong> {{ desc }}
            </p>
            <p>
              Tools : 
              <template v-for="item in tools" :key="item">
                <strong>{{ item }}, </strong>
              </template>
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
import CategoryLabel from './work/CategoryLabel.vue'

export default {
  name: 'Work',
  components: {
    Showcase,
    CategoryLabel
  },
  data() {
    return {
      projects: [],
      title: '',
      desc: '',
      projMade: '',
      gallery: [],
      tools: [],
      lecture: '',
      showModal: false,
      projCatArr: [],
      projCategory: 'All'
    }
  },
  created() {
    this.projects = [
      {
        id: 1,
        title: 'JagaJogja',
        category: 'web',
        desc: 'adalah portal laporan keamanan, kebersihan, dan fasilitas umum untuk mewujudkan Jogja Smart city.',
        link: '',
        projMade: '2019 (Semester 3)',
        mainImage: 'pabw/homepage.png',
        gallery: ['pabw/daftarlaporan.png', 'pabw/input laporan.png', 'pabw/tentang.png'],
        tools: ['HTML', 'CSS', 'Bootstrap 4', 'Laravel Framework'],
        lecture: 'Pengembangan Aplikasi Berbasis Web'
      },
      {
        id: 2,
        title: 'EzTourism',
        category: 'web',
        desc: 'adalah platform jasa pemesanan oleh-oleh khas Jogja dan menyediakan pelayanan jasa sewa tour guide wisata bagi para wisatawan yang hendak berkeliling menikmati keindahan “kota gudeg” ini untuk meminimalisir kendala kebutuhan dalam berwisata.',
        link: '',
        projMade: '2020 (Semester 4)',
        mainImage: 'psi/ez1.png',
        gallery: ['psi/ez1.png', 'psi/ez2.png', 'psi/ez3.png'],
        tools: ['HTML', 'CSS', 'Bootstrap 4', 'Laravel Framework'],
        lecture: 'Pengembangan Sistem Informasi'
      },
      {
        id: 3,
        title: 'Dojo Blog',
        category: 'web',
        desc: 'A simple CRD (CREATE - READ - DELETE) blog web apps built using ReactJS, a ReactJS tutorial by Net Ninja (Shaun Pelling)',
        link: 'https://dojo-blog-react.vercel.app/',
        projMade: 'March 2021',
        mainImage: 'dojo-blog/dojo1.png',
        gallery: ['dojo-blog/dojo1.png', 'dojo-blog/dojo2.png', 'dojo-blog/dojo3.png'],
        tools: ['HTML', 'CSS', 'JavaScript','React JS'],
        lecture: 'React JS Tutorial by Net Ninja (Shaun Pelling)'
      },
      {
        id: 4,
        title: 'Single Web Author Page',
        category: 'web',
        desc: 'a single web page for my submission in Dicoding Courses',
        link: '',
        projMade: 'August 2020',
        mainImage: 'basic-web/web1.png',
        gallery: ['basic-web/web1.png'],
        tools: ['HTML', 'CSS'],
        lecture: 'Basic Web Programming (Dasar Pemrograman Web) by Dicoding Indonesia'
      },
      {
        id: 5,
        title: 'Task Tracker App',
        category: 'web',
        desc: 'a single web page task tracker web apps',
        link: 'https://vue-task-tracker-iota.vercel.app/',
        projMade: 'May 2021',
        mainImage: 'vue-task/task1.png',
        gallery: ['vue-task/task1.png'],
        tools: ['HTML', 'CSS', 'JavaScript', 'Vue JS'],
        lecture: 'Vue Crash Course by Traversy Media (Brad Traversy)'
      }
    ]
  }, 
  computed: {
    webCounter: function() {
      return this.projects.filter((item) => item.category === 'web').length;
    },
    mobileCounter: function() {
      return this.projects.filter((item) => item.category === 'mobile').length;
    },
    gameCounter: function () {
      return this.projects.filter((item) => item.category === 'game').length;
    },
    allCounter: function () {
      return this.projects.length;
    }
  },
  methods: {
    toggleModal(project) {
      this.showModal = !this.showModal;
      this.title = project.title;
      this.desc = project.desc;
      this.projMade = project.projMade;
      this.gallery = project.gallery;
      this.tools = project.tools;
      this.lecture = project.lecture;
    },
    toggleCategory(term) {
      if (term.toLowerCase() === 'web development') {
        this.projCategory = term;
        this.projCatArr = this.projects.filter((item) => item.category === 'web');
      } else if (term.toLowerCase() === 'mobile apps development') {
        this.projCategory = term;
        this.projCatArr = this.projects.filter((item) => item.category === 'mobile');
      } else if (term.toLowerCase() === 'game development') {
        this.projCategory = term;
        this.projCatArr = this.projects.filter((item) => item.category === 'game');
      } else if (term.toLowerCase() === 'all') {
        this.projCategory = term;
      }
    }
  }
}
</script>