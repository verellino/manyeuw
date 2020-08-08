<template>
  <section class='highlight content-section'>
    <div class="highlight-left">
      <prismic-rich-text class="ylttl" :field="slice.primary.title"/>
      <prismic-rich-text :field="slice.primary.richtext"/>
      <p>
        <prismic-link :field="slice.primary.link">{{ $prismic.asText(slice.primary.link_label) }} ›</prismic-link>
      </p>
    </div>
    <div class="highlight-right">
      <prismic-image :field="slice.primary.featured_image"/>
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'image-highlight'
}
</script>

<style lang="sass" scoped>
.highlight
  padding-top: 20px
  position: relative
  overflow: auto
  
.highlight-left
  width: 50%
  float: left
  position: absolute
  z-index: 2
  padding: 30px 20px 0
  background: #efdc7c
  a
    color: #000000
  a:hover
    color: #0A2B43

.highlight-right
  width: 90%
  float: right
  margin-top: 50px
  img
    width: 100%


@media (max-width: 767px)
  .content-section
    margin-bottom: 2rem
  .highlight
    overflow: none
 
  .highlight-left, .highlight-right
    position: relative
    width: fit-content
    float: none
  .highlight-left
    padding: 20px 20px 5px
  .highlight-right
    margin-top: 20px
</style>

