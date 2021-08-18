<template>
    <div class="v-catalog">
    <h1>Catalog</h1>
    <v-catalog-item
        v-for="product in PRODUCTS"
        :key="product.article"
        v-bind:product_data="product"
        @sendDataToParent="showChildArticeInConsole"
    />
    </div>
</template>

<script>
    import vCatalogItem from './v-catalog-item.vue'
    import {mapActions, mapGetters} from 'vuex'

    export default {
      name: 'v-catalog',
      components: {
          vCatalogItem
      },
      props: {},
      data() {
        return {

        }
      },
      computed: {
          ...mapGetters([
              'PRODUCTS'
          ])
      },
      methods: {
          ...mapActions([
              'GET_PRODUCTS_FROM_API'
          ]),
          showChildArticeInConsole(data) {
              console.log(data);
          }
      },
      watch: {},
      mounted() {
          this.GET_PRODUCTS_FROM_API()
          .then((response) => {
              if (response.data) {
                  console.log('Data arrived!')
              }
          })
      }
    }
</script>

<style lang="scss">
  .v-catalog {
      &__list {
          display: flex;
          flex-wrap: wrap;
          justify-content: space-between;
          align-items: center;
      }
  }
</style>