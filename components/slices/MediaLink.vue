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

.media-item
   width: 250px
   margin-right: 50px

a:hover
    border-style: solid
</style>