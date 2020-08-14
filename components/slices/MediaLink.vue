<template>
  <section class="media-sec">
    <div v-for="item in slice.items" :key="item.id" class="media-item">
     <prismic-link :field="item.media_link" class="medlink">
         <prismic-image :field="item.link_cover" class="link-img"/>
         <h3>{{ $prismic.asText(item.link_title) }}</h3>
    </prismic-link>
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'media-link'
}
</script>
<style lang="sass" scoped>
.media-sec
    display: flex
    flex-wrap: wrap
    text-align: center
    justify-content: space-between
    margin-bottom: 100px

.media-item
   width: 29%
   margin-bottom: 25px

.medlink
  width: 100%
  h3
    padding: 0 10px
a:hover
    border-style: solid

@media (max-width: 767px)
  .media-sec
    margin-bottom: 40px
  .media-item
    width: 100%
</style>