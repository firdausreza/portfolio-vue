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

    </div>
  </div>
</template>

<script>
import ResumeCard from './education/ResumeCard.vue'

export default {
  name: 'Career',
  components: {
    ResumeCard
  }
}
</script>