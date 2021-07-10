<template>
  <div class="col-md-6 col-sm-12 my-2">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title fw-bold">{{ name }}</h5>
        <hr>
        <p v-if="template !== true" class="card-text text-wrap">{{ desc }}</p>
        <p v-else-if="template === true && desc === 'webcare'" class="card-text text-wrap" v-html="webcareTemp"></p>
      </div>
      <div class="card-footer text-muted">
        {{ period }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ResumeCard',
  data() {
    return {
      webcareTemp: `I am Co-Founder and Web Developer in Webcare.idn, webcare is a startup company that provides a 
      web-making services for low to middle level entrepreneur in Indonesia. You can find out more about the company <a target='_blank' rel='noreferrer noopener' href='https://webcareidn.com/'>here</a>.
      (I am <strong>currently inactive</strong> from the company).`
    }
  },
  props: {
    name: String,
    desc: String,
    period: String,
    template: Boolean
  }
}
</script>