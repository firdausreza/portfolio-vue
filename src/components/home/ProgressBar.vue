<template>
  <div class="col-md-6 col-lg-6 col-sm-12">
    <h4>
      <span>
        <i :class="icon"></i>
      </span>
      {{ name }}
    </h4>
    <div class="progress mb-3">
      <div class="progress-bar progress-bar-striped progress-bar-animated bg-success" 
        role="progressbar" 
        aria-valuemin="0" 
        aria-valuemax="100"
        :style="{width}">
          {{ width }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProgressBar',
  props: {
    name: String,
    width: String,
    icon: String
  }
}
</script>