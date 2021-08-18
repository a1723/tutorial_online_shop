<template>
    <div class="v-main-wrapper">
    <p>{{title}}</p>
    <vCatalog></vCatalog>
    <vCart></vCart>
    </div>
</template>

<script>
    import vCatalog from './v-catalog.vue'
    import vCart from './v-card.vue'

    export default {
      name: 'v-main-wrapper',
      components: {
          vCatalog,
          vCart
      },
      props: {},
      data() {
          return {
              title: 'Main wrapper'
          }
      },
      computed: {},
      methods: {},
      watch: {},
      mounted() {
          console.log('Hellom, I am alive!')
      }
    }
</script>

<style>
    .v-main-wrapper{
    max-width: 900px;
    margin: 0 auto;
    }
</style>