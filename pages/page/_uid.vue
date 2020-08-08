<template>
  <section>
    <!-- Slices block component -->
    <h1 class="page-title container">{{$prismic.asText(title)}}</h1>
    <slices-block :slices="slices"/>
  </section>
</template>

<script>
// Imports for Prismic Slice components
import SlicesBlock from '~/components/SlicesBlock.vue'

export default {
  name: 'page',
  components: {
    SlicesBlock
  },
  head () {
    return {
      title: 'MANYEUW',
    }
  },
  async asyncData({ $prismic, params, error }) {
    try{
      // Query to get post content
      const document = (await $prismic.api.getByUID('page', params.uid)).data

      return {
        // Set slices as variable
        title: document.title,
        slices: document.page_content
      }
    } catch (e) {
      // Returns error page
      error({ statusCode: 404, message: 'Page not found' })
    }
  },
}
</script>
<style scoped>
.page-title{
  margin: 40px auto 20px;
  width: 100%;
  
}
</style>