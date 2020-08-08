<template>
  <section class='embed-video content-section'>
    <prismic-embed class="video" :field="slice.primary.video"/>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'video-slice'
}
</script>

<style lang="sass" scoped>
.embed-video 
  position: relative
  width: 100%
  height: 0
  padding-bottom: 56.25%

.video 
    position: absolute
    top: 0
    left: 0
    width: 100%
    height: 100%
    iframe
      width: 100%

</style>
