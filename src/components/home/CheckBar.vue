<template>
  <div class="col-6">
    <div class="fw-bold fs-5">
      {{ name }}
      <span>
        <i :class="icon" style="color: green"></i>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CheckBar',
  props: {
    name: String,
    icon: String
  }
}
</script>