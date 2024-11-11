<template>
  <div>
     <News />
     <AddEditDia />
  </div>
</template>

<script>
  import News from './components/News.vue'
  import AddEditDia from './components/AddEditDia.vue'
  export default {
    components: {
      News,
      AddEditDia
    }
  }
</script>

<style scoped>

</style>