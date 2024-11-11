<template>
  <div>
     <NewsComponent @showAddDia="showAddDia" :list="list"/>
     <AddEditDia ref="addEditDia" @sendNewsData="sendNewsData"/>
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
    data() {
      return {
        no: 1,
        list: [
            {
                id: 1,
                title: '娱乐',
                content: '娱乐新闻'
            },
            {
                id: 2,
                title: '体育',
                content: '体育新闻'
            },
            {
                id: 3,
                title: '科技',
                content: '科技新闻'
            }
        ]
      }
    },
    methods: {
      showAddDia(visible) {
        this.$refs.addEditDia.visible = visible
      },
      sendNewsData(item) {
        this.list.push({
          id: this.no++,
          title: item.title,
          content: item.content
        })
      }
    }
  }
</script>

<style scoped>

</style>