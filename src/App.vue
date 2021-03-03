<template>
  <div id="app">
    <BreadCrumbs />
    <CatalogHeader 
      @handleMaterial='materialSort'
      @handlePrice='priceSort'
    />
    <Catalog 
      v-bind:cards='cards'
    />
  </div>
</template>

<script>
import BreadCrumbs from '@/components/BreadCrumbs';
import CatalogHeader from '@/components/CatalogHeader';
import Catalog from '@/components/Catalog';
import date from '@/date/items.json';


export default {
  name: 'App',
  data() {
    return{
      cards: date,
      
    }
  },
  components: {
    BreadCrumbs,
    CatalogHeader,
    Catalog,
  },
  methods: {
    materialSort(material){
      if(material !== 'metal'){
        this.cards.sort((a, b) => {
          if(a.material > b.material){
            return 1
          }
          if(a.material < b.material){
            return -1
          }
          return 0
        })
      } else{
        this.cards.sort((a, b) => {
          if(a.material < b.material){
            return 1
          }
          if(a.material > b.material){
            return -1
          }
          return 0
        })
      }
    },
    priceSort(price){
      if(price === 'ascending'){
        this.cards.sort((a, b) => {
          if(a.price.current_price > b.price.current_price){
            return 1
          }
          if(a.price.current_price < b.price.current_price){
            return -1
          }
          return 0
        })
      } else{
        this.cards.sort((a, b) => {
          if(a.price.current_price < b.price.current_price){
            return 1
          }
          if(a.price.current_price > b.price.current_price){
            return -1
          }
          return 0
        })
      }
    }
  }
}
</script>

<style>

</style>
