<template>
  <div class="card">
    <img :src="require(`@/assets/img/${project.mainImage}`)" alt="" class="card-img-top">
    <div class="card-body">
      <h5 class="card-title"><strong>{{ project.title }}</strong></h5>
      <a class="btn btn-success" @click="$emit('toggle-modal')" data-bs-toggle="modal" data-bs-target="#cardModal" :key="project.id">Detail</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Showcase',
  props: {
    project: {
      type: Object,
    }
  }
}
</script>