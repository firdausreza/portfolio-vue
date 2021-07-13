<template>
  <template v-if="catName.toLowerCase() === 'web development'">
    <div @click="$emit('toggle-category', catName)" class="category-label bg-dark text-white my-2">
      <p style="margin: 0;">{{ catName }} (<strong>{{ total }}</strong>)</p>
    </div>
  </template>
  <template v-else-if="catName.toLowerCase() === 'mobile apps development'">
    <div @click="$emit('toggle-category', catName)" class="category-label bg-dark text-white my-2">
      <p style="margin: 0;">{{ catName }} (<strong>{{ total }}</strong>)</p>
    </div>
  </template>
  <template v-else-if="catName.toLowerCase() === 'game development'">
    <div @click="$emit('toggle-category', catName)" class="category-label bg-dark text-white my-2">
      <p style="margin: 0;">{{ catName }} (<strong>{{ total }}</strong>)</p>
    </div>
  </template>
  <template v-else>
    <div @click="$emit('toggle-category', catName)" class="category-label bg-dark text-white my-2">
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