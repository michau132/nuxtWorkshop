<template>
  <div class="d-flex">
    <div v-for="(article, index) in articles" :key="index">
      <nuxt-link :to="`posty/${article.slug}`">
        <v-card min-width="300px" max-width="300px" class="ma-5 pa-3">
          <v-card-title>
            {{ article.title }}
          </v-card-title>
          <v-img :src="article.imgURL"></v-img>
          <v-card-text>{{ article.desc }}</v-card-text>
        </v-card>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data: () => ({
    articles: []
  }),
  created() {
    const req = require.context('~/articles', false, /\.(md)$/)
    req.keys().forEach((element) => {
      const key = element.replace('./', '').replace('.md', '')
      const { attributes } = require(`~/articles/${key}.md`)
      this.articles.push({ ...attributes, slug: key })
    })
  }
}
</script>
