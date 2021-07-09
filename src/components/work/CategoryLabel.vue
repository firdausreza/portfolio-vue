<template>
  <template v-if="catName.toLowerCase() === 'web development'">
    <div @click="$emit('toggle-category', catName)" class="category-label bg-info text-white">
      <p style="margin: 0;">{{ catName }} (<strong>{{ total }}</strong>)</p>
    </div>
  </template>
  <template v-else-if="catName.toLowerCase() === 'mobile apps development'">
    <div @click="$emit('toggle-category', catName)" class="category-label bg-danger text-white">
      <p style="margin: 0;">{{ catName }} (<strong>{{ total }}</strong>)</p>
    </div>
  </template>
  <template v-else-if="catName.toLowerCase() === 'game development'">
    <div @click="$emit('toggle-category', catName)" class="category-label bg-success text-white">
      <p style="margin: 0;">{{ catName }} (<strong>{{ total }}</strong>)</p>
    </div>
  </template>
  <template v-else>
    <div @click="$emit('toggle-category', catName)" class="category-label bg-primary text-white">
      <p style="margin: 0;">{{ catName }} (<strong>{{ total }}</strong>)</p>
    </div>
  </template>
</template>

<script>
export default {
  name: 'CategoryLabel',
  props: {
    catName: {
      type: String
    },
    total:{
      type: Number
    }
  }
}
</script>