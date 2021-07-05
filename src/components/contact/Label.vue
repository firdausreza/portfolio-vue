<template>
  <div class="col-md-3 col-lg-3 col-sm-12 my-4">
    <div class="label-card">
      <img :src="require(`@/assets/icon/${icon}.png`)" class="icon-img" :alt="icon">
      <a :href="srcLink" target="_blank" class="link-value">{{ value }}</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Label',
  props: {
    srcLink: String,
    icon: String,
    value: String
  }
}
</script>