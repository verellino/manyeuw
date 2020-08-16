<template>
  <div class="bg-yellow">
    <footer class="footer">
      <div class="foothead">
        <nuxt-link to="/" class="logo">
          <prismic-image :field="$store.state.menu.site_logo"/>
        </nuxt-link>
        <h2>Manyeuw</h2>
      </div>
      <ul class="footer-links">
          <li v-for="menuLink in $store.state.menu.menu_links" :key="menuLink.id">
            <prismic-link :field="menuLink.link">{{ $prismic.asText(menuLink.label) }}</prismic-link>
          </li>
      </ul>
      <div class="copyright">
        <p>©KKN PPM UGM MANYEUW 2020, ALL RIGHTS RESERVED</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'FooterPrismic'
}
</script>

<style lang="sass" scoped>
.bg-yellow
  width: calc(100% + 40px)
  background: #efdc7c
  margin: 0 -20px -20px
.footer
  padding: 40px 0 5px
  margin: 0 auto
  text-align: left
  border-top: 1px solid #DADADA
  h2
  font-weight: 600
  color: #0A2B43
  ul
    padding-left: 15px

.foothead
  display: flex
  align-items: center

.logo
  display: inline-block
  margin-right: 15px
  img
    width: 60px

.footer-links
  display: flex
  flex-direction: column
  text-decoration: none
  li
    display: inline-block
    a:hover
      color: #0A2B43

.copyright
  font-size: 10px
  text-align: center
  p
    margin: 0
@media (max-width: 767px)
  .bg-yellow
    width: calc(100% + 20px)
    margin: 0 -10px -10px
  .footer
    padding: 20px 20px 5px
</style>
