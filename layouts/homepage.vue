<template>
  <div class="homepage">
    <header-prismic/>
    <nuxt />
    <video-youtube/>
    <footer-prismic/>
  </div>
</template>

<script>
import HeaderPrismic from '~/components/HeaderPrismic.vue'
import VideoYoutube from '~/components/VideoYoutube.vue'
import FooterPrismic from '~/components/FooterPrismic.vue'

export default {
  components: {
    HeaderPrismic,
    VideoYoutube,
    FooterPrismic
  },
  head () {
    return {
      title: 'Manyeuw',
    }
  },
  // Called before rendering the layout (even for error page)
  async middleware({ store, $prismic }) {
    await store.dispatch('fetchMenu', $prismic)
  }
}
</script>
