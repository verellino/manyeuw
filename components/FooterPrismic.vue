<template>
  <div class="bg-yellow">
    <footer class="footer">
      <div class="logo"></div>
      <h2>Manyeuw</h2>
      <ul class="footer-links">
          <li v-for="menuLink in $store.state.menu.menu_links" :key="menuLink.id">
            <prismic-link :field="menuLink.link">{{ $prismic.asText(menuLink.label) }}</prismic-link>
          </li>
      </ul>
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
  width: 100%
  background: #efdc7c
.footer
  padding: 40px 0
  margin: 0 auto
  text-align: left
  border-top: 1px solid #DADADA
  h2
  font-weight: 600
  color: #0A2B43

.logo
  width: 100px

.footer-links
  display: flex
  flex-direction: column
  text-decoration: none
  li
    display: inline-block
    a:hover
      color: #0A2B43
</style>
