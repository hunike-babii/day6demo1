<template>
  <div>
     <NewsComponent @showAddDia="showAddDia"/>
     <AddEditDia ref="addEditDia"/>
  </div>
</template>

<script>
  import NewsComponent from './components/NewsComponent.vue'
  import AddEditDia from './components/AddEditDia.vue'
  export default {
    components: {
      NewsComponent,
      AddEditDia
    },
    methods: {
      showAddDia(visible) {
        this.$refs.addEditDia.visible = visible
      }
    }
  }
</script>

<style scoped>

</style>