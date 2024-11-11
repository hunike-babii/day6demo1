<template>
  <div>
     <NewsComponent />
     <AddEditDia />
  </div>
</template>

<script>
  import NewsComponent from './components/NewsComponent.vue'
  import AddEditDia from './components/AddEditDia.vue'
  export default {
    components: {
      NewsComponent,
      AddEditDia
    }
  }
</script>

<style scoped>

</style>