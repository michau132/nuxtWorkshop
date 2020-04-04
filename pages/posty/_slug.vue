<template>
  <div class="container">
    <div class="pa-10">
      <component :is="selectedArticle" />
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    attributes: {},
    selectedArticle: null
  }),
  created() {
    const markdown = require(`~/articles/${this.$route.params.slug}.md`)
    this.attributes = markdown.attributes
    this.selectedArticle = markdown.vue.component
  }
}
</script>
