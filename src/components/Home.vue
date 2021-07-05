<template>
  <div id="home" class="collapse show" data-bs-parent="#accordion">
    <div class="card card-body bg-primary text-white p-5">
      <h2>Welcome to my portfolio!</h2>
    </div>

    <div class="card card-body p-5">
      <h3>About Me :</h3>
      <p style="text-align: justify;">
        You can call me Reza/Ali, both is fine. I'm 20 years old currently and live in Yogyakarta, I'm a 3rd year student (2018) and studying on 
        Bachelor Degree of Informatics at Islamic University of Indonesia. I'm highly interested in Front End Web Development, i have 2+ years in Front End Development (Using Html, CSS, Vanilla JS), 1+ years in Back End Development (Using Laravel)
        , and 1+ years in Game Development (Using Unity Engine). I'm currently open and ready to work on profit/non-profit projects, so feel free to ask and/or negotiate
        with me (See on Contacts).
      </p>

      <hr>

      <h3 style="text-align: center; margin-bottom: 20px;">Technical Skills</h3>

      <div class="row">
        <ProgressBar name="HTML" width="90%" icon="fab fa-html5" />
        <ProgressBar name="CSS" width="60%" icon="fab fa-css3-alt" />
      </div>

      <div class="row">
        <ProgressBar name="Javascript" width="75%" icon="fab fa-js" />
        <ProgressBar name="Java" width="60%" icon="fab fa-java" />
      </div>

      <div class="row">
        <ProgressBar name="UI Design" width="85%" icon="fas fa-pencil-alt" />
        <ProgressBar name="Bootstrap" width="90%" icon="fab fa-bootstrap" />
      </div>

      <div class="row">
        <ProgressBar name="ReactJS*" width="60%" icon="fab fa-react" />
        <ProgressBar name="VueJS*" width="65%" icon="fab fa-vuejs" />
      </div>

      <div class="row">
        <ProgressBar name="Laravel" width="60%" icon="fab fa-laravel" />
        <ProgressBar name="Unity and C#" width="75%" icon="fab fa-unity" />
      </div>

      <p class="text-muted">*still learning</p>
      
      <hr>

      <h3 class="mb-5" style="text-align: center;">I am ...</h3>

      <div class="row">
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Creative" icon="fas fa-check-circle"/>
        </div>
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Good in communication"  icon="fas fa-check-circle"/>
        </div>
      </div>

      <div class="row">
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Adapt easily" icon="fas fa-check-circle"/>
        </div>
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Hard worker"  icon="fas fa-check-circle"/>
        </div>
      </div>

      <div class="row">
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Responsible" icon="fas fa-check-circle"/>
        </div>
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Good in critical thinking"  icon="fas fa-check-circle"/>
        </div>
      </div>

      <div class="row">
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Have a high curiosity" icon="fas fa-check-circle"/>
        </div>
        <div class="col-md-6 col-lg-6 col-sm-12 d-flex justify-content-center text-center mb-3">
          <CheckBar name="Quick learner"  icon="fas fa-check-circle"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProgressBar from './home/ProgressBar.vue'
import CheckBar from './home/CheckBar.vue'

export default {
  name: 'Home',
  components: {
    ProgressBar,
    CheckBar
  }
}
</script>