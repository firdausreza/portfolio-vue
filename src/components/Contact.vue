<template>
  <div id="contact" class="collapse" data-bs-parent="#accordion">
    <div class="card card-body bg-danger text-white p-5">
      <h2>Stay connected!</h2>
    </div>

    <div class="card card-body p-5">
      <div class="row mb-5">
        <div class="col-12">
          <h3 class="mb-3 text-center">Email Form</h3>
          <form ref="emailform" id="emailForm" class="contact-form" @submit.prevent="sendEmail">
            <div class="mb-3">
              <label for="nameField" class="form-label">Nama</label>
              <input type="text" class="form-control" name="name" id="nameField" v-model="mail.name" placeholder="Nama lengkap...">
            </div>
            <div class="mb-3">
              <label for="emailField" class="form-label">Email Address</label>
              <input type="email" class="form-control" name="email" id="emailField" v-model="mail.email" placeholder="Alamat email...">
            </div>
            <div class="mb-3">
              <label for="subjectField" class="form-label">Subject</label>
              <input type="text" class="form-control" name="subject" id="subjectField" v-model="mail.subject" placeholder="Email subject...">
            </div>
            <div class="mb-3">
              <label for="messageField" class="form-label">Pesan</label>
              <textarea name="message" rows="5" class="form-control" id="messageField" v-model="mail.message" placeholder="Isi pesan..."></textarea>
            </div>
            <div class="d-grid">
              <input class="btn btn-danger" type="submit" value="submit">
            </div>
          </form>
        </div>
      </div>
      <div class="row">
        <h3 class="mb-3 text-center">Social Media</h3>
        <Label srcLink="https://wa.link/zo8m24" icon="whatsapp" value="+62 877-3685-4821" />
        <Label srcLink="https://www.linkedin.com/in/rezafirdaus080/" icon="linkedin" value="Reza Firdaus" />
        <Label srcLink="https://github.com/firdausreza" icon="github" value="@firdausreza" />
        <Label srcLink="https://www.instagram.com/mhmmdrezalif/" icon="instagram" value="@mhmmdrezalif" />
      </div>
    </div>
  </div>
</template>

<script>
import Label from './contact/Label.vue'
import emailjs from 'emailjs-com'

export default {
  name: 'Contact',
  components: {
    Label
  }, 
  data() {
    return {
      mail: {
        name: this.name,
        email: this.email,
        subject: this.subject,
        message: this.message
      }
    }
  },
  methods: {
    sendEmail() {
      const objMail = {
        user_name: this.mail.name,
        user_email: this.mail.email,
        user_subject: this.mail.subject,
        user_message: this.mail.message
      }
      emailjs.send('service_dikyf6v', 'template_0rzntq6', objMail, 'user_6baA8HMJvyYoR2mqK3AiO')
      .then((result) => {
        console.log('SUCCESS!', result.status, result.text);
        this.$refs.emailform.reset();
        alert('Email berhasil dikirim!');
        }, (error) => {
        console.log('FAILED...', error);
        alert('Gagal mengirim email!')
      });
    }
  }
}
</script>