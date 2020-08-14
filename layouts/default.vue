<template>
  <div>
    <header-prismic/>
    <SideNav/>
    <nuxt />
    <footer-prismic/>
  </div>
</template>

<script>
import HeaderPrismic from '~/components/HeaderPrismic.vue'
import FooterPrismic from '~/components/FooterPrismic.vue'
import SideNav from '~/components/SideNav.vue'


export default {
  components: {
    HeaderPrismic,
    FooterPrismic,
    SideNav
  },
  head () {
    return {
      title: 'Manyeuw',
    }
  },
  // Called before rendering the layout (even for error page)
  async middleware({ store, $prismic }) {
    await store.dispatch('fetchMenu', $prismic)
  },
  computed: {
    isSidebar() {
      return this.$store.getters['nav/toggleSidebar']
      }
    },
    watch: {
     '$route': function() {
        if (process.client && this.isSidebar && window.innerWidth < 768) {
          this.$store.dispatch('nav/toggleSidebar')
        }
      },
    }
}
</script>