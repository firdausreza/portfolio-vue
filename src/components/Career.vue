<template>
  <div id="career" class="collapse" data-bs-parent="#accordion">
    <div class="card card-body bg-success text-white p-5">
      <h2>Education and Job History</h2>
    </div>

    <div class="card card-body p-5">
      <h3 class="mb">Education History</h3>

      <div class="row">
        <ResumeCard 
          name="SDN 15 Tangerang"
          desc="Miss my childhood"
          period="2008 - 2012"
        />
        <ResumeCard 
          name="SMPN 5 Tangerang"
          desc="Starting to have an interests and having joyful life"
          period="2012 - 2015"
        />
        <ResumeCard 
          name="SMA Unggulan Amanatul Ummah"
          desc="Memories can not be forgotten here"
          period="2015 - 2018"
        />
        <ResumeCard 
          name="Universitas Islam Indonesia"
          desc="Studying on Bachelor Degree of Informatics"
          period="2018 - Present"
        />
      </div>

      <hr class="my-5" />

      <h3 class="mb-3">Job History</h3>

      <div class="row">
        <ResumeCard 
            name="Co-Founder and Web Developer at Webcare.idn"
            desc="webcare"
            period="Aug 2020 - Present"
            :template="true"
          />
      </div>

      <hr class="my-5" />

      <h3 class="mb-3">Certificate and Achievement</h3>

      <div class="row">
        <template v-for="item in certificates" :key="item.id">
          <div class="col-lg-3 col-md-3 col-sm-12 m-3">
            <img id="cerfImg" :src="require(`@/assets/img/${item.src}`)" :alt="item.name" width="300" height="200" @click="toggleImgModal(item)" data-bs-toggle="modal" data-bs-target="#imgModal">
          </div>
        </template>
      </div>
    </div>
  </div>
  
  <div class="modal fade" id="imgModal" tabindex="-1" aria-hidden="true">
    <div class="modal-dialog modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">{{ imgName }}</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <img style="width: 100%; height: 100%;" class="modal-image" v-if="imgSrc !== ''" :src="require(`@/assets/img/${imgSrc}`)" :alt="imgName">
        </div>
        <div class="modal-footer">
          <div class="w-100">
            <p>Date Achieved : <strong>{{ imgAchieved }}</strong></p>
            <p>Valid Until : <strong>{{ imgValid }}</strong></p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ResumeCard from './education/ResumeCard.vue'

export default {
  name: 'Career',
  components: {
    ResumeCard
  },
  data() {
    return {
      certificates: [],
      imgName: '',
      imgSrc: '',
      imgAchieved: '',
      imgValid: '',
      showModal: false
    }
  },
  created() {
    this.certificates = [
      {
        id: 1,
        name: 'Pengenalan ke Dasar Pemrograman (Basic Programming 101)',
        achieved: 'Feb 28, 2021',
        validUntil: 'Feb 28, 2024',
        src: 'certificate/basic-programming.jpg'
      },
      {
        id: 2,
        name: 'Belajar Dasar Pemrograman Javascript',
        achieved: 'May 17, 2021',
        validUntil: 'May 17, 2024',
        src: 'certificate/basic-js.jpg'
      },
      {
        id: 3,
        name: 'Belajar Dasar Pemrograman Web',
        achieved: 'Aug 6, 2020',
        validUntil: 'Aug 6, 2023',
        src: 'certificate/basic-web.jpg'
      },
      {
        id: 4,
        name: 'Belajar Membuat Front-End Web untuk Pemula',
        achieved: 'Jun 7, 2021',
        validUntil: 'Jun 7, 2024',
        src: 'certificate/front-end-web.jpg'
      },
      {
        id: 5,
        name: 'Belajar Membuat Aplikasi Back-End untuk Pemula',
        achieved: 'May 31, 2021',
        validUntil: 'May 31, 2021',
        src: 'certificate/back-end-web.jpg'
      }
    ]
  },
  methods: {
    toggleImgModal(item) {
      console.log(item)
      this.showModal = !this.showModal
      this.imgName = item.name
      this.imgSrc = item.src
      this.imgAchieved = item.achieved
      this.imgValid = item.validUntil
    }
  }
}
</script>

<style scoped>
#cerfImg {
  border-radius: 5px;
  cursor: pointer;
}
</style>