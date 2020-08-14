<template>
  <header class="site-header">
    <p v-if="$store.state.menu === 'Please create a menu document'" class="logo">{{ $store.state.menu }}</p>
    <nuxt-link to="/" class="logo">
       <prismic-image :field="$store.state.menu.site_logo"/>
    </nuxt-link>
    <nav>
      <ul class="desktop-nav">
        <li v-for="menuLink in $store.state.menu.menu_links" :key="menuLink.id">
          <prismic-link :field="menuLink.link">{{ $prismic.asText(menuLink.label) }}</prismic-link>
        </li>
      </ul>
      <div class="drawer-toggle" role="button" @click="$store.dispatch('nav/toggleSidebar')">
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
      </div>
      <div class="app-links">
        <AppLinks/>
      </div>
    </nav>
    
  </header>
</template>

<script>
import AppLinks from '~/components/AppLinks.vue'

export default {
  name: 'header-prismic',
  components: {
    AppLinks
  },
}
</script>

<style lang="sass">    
.site-header
  height: 30px
  padding: 20px 0
  color: #0A2B43
  font-weight: 700
  display: flex
  justify-content: space-between
  align-items: center
  a
    color: #484d52
    font-weight: 700
  nav a:hover
    color: #0A2B43

.homepage .site-header
  color: #ffffff
  a
    color: #ffffff
  nav a:hover
    color: #0A2B43

.site-header
  .logo
    width: 70px
    display: inline-block
    font-size: 22px
    font-weight: 900
  nav
    float: right
    ul
      margin: 0
      padding-left: 0
    li
      display: inline-block
      margin-left: 40px

.app-links 
   display: none
   justify-self: end
.drawer-toggle 
  display: none
@media (max-width: 1060px)
  .site-header
    padding-left: 20px
    padding-right: 20px

@media (max-width: 767px)
  .desktop-nav
    display: none
  .site-header
    height: auto
    display: flex
    justify-content: space-between
    align-items: center

  .homepage .site-header
    position: absolute
    left: 0
    right: 0

  .site-header
    .logo
      display: block
      text-align: center
    nav
      float: none
      text-align: center
      li
        display: inline-block
        margin-left: 10px
        margin-right: 10px
  .drawer-toggle .bar 
    width: 90%
    height: 2px
    background-color: black
    
  .drawer-toggle 
    display: flex
    justify-self: end
    flex-direction: column
    justify-content: space-around
    height: 25px
    width: 30px
    padding-right: 16px
    cursor: pointer
    
</style>


