<template>
  <section class='embed-video content-section'>
    <prismic-embed :field="slice.primary.video"/>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'video-slice'
}
</script>

<style lang="sass" scoped>

</style>
