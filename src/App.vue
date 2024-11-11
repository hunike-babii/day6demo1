<template>
  <div>
     <NewsComponent @showAddDia="showAddDia" :list="list" @edit="edit"/>
     <AddEditDia ref="Dia" @editNewsData="editNewsData" @changeNewsData="changeNewsData"/>
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
        no: 0,
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
        this.$refs.Dia.visible = visible
      },
      editNewsData(item) {
        this.list.push({
          id: this.no++,
          title: item.title,
          content: item.content
        })
      },
      edit(item) {
        this.$refs.Dia.visible = true
        this.$refs.Dia.type = 2
        this.$refs.Dia.id = item.id
        this.$refs.Dia.title = item.title
        this.$refs.Dia.content = item.content
      },
      changeNewsData(item) {
        const index = this.list.findIndex(v => v.id === item.id);
        if (index !== -1) {
          this.list[index].title = item.title;
          this.list[index].content = item.content;
        }
      }
    }
  }
</script>

<style scoped>

</style>