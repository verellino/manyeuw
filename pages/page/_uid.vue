<template>
  <section>
    <section class="hero" :style="{ backgroundImage: 'linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.4)), url(' + heroimg.url + ')' }">
      <div class="page-title">
        <h1 class="header-page">{{ title }}</h1>
      </div>
    </section>
    <!-- Slices block component -->
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
  async asyncData({ $prismic, params, error }) {
    try{
      // Query to get post content
      const document = (await $prismic.api.getByUID('page', params.uid)).data

      return {
        title: document.title[0].text,
        heroimg: document.hero_img,
        // Set slices as variable
        slices: document.page_content
      }
    } catch (e) {
      // Returns error page
      error({ statusCode: 404, message: 'Page not found' })
    }
  },
  head () {
    return {
      title: this.title
    }
  },
}
</script>
<style scoped>
.hero{
  margin: 40px 0 100px;
  max-height: 30vh;
  padding: 30em 20px 0;
  background-position: center center;
  background-size: cover;
  position: relative;
} 
.header-page{
  font-size: 4vw;
}
.page-title{
  background: #efdc7c;
  padding: 3em 8em;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: absolute;
  bottom: -60px;
  left: 10px
}
@media (min-width: 768px) {
  .header-page{
    font-size: calc(1vw + 46px);
    margin: 0;
  }
}
@media (max-width: 767px) {
  .hero{
    margin: 20px 0 60px;
    height: 50vh;
    padding: 0;
  }
  .page-title{
    padding: 1em 2em;
    bottom: -30px;
  }
  .header-page{
    font-size: 32px;
    margin: 0;
  }
}
@media (max-width: 381px) {
  .header-page{
    font-size: 24px;
    margin: 0;
  }
  .page-title{
    padding: 1em;
  }
}
</style>