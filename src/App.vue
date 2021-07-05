<template>
  <div id="accordion" class="container accordion">
    <Header />
    <div id="content">
      <Home />
      <Career />
      <Work />
      <Contact />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Home from './components/Home.vue'
import Career from './components/Career.vue'
import Work from './components/Work.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Home,
    Career,
    Work,
    Contact,
    Footer
  }
}
</script>

<style>
@import url('./assets/style/main.css');
</style>
