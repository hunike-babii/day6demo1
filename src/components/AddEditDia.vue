<template>
  <el-dialog
    v-model="visible"
    :title="type === 1 ? '添加新闻' : '编辑新闻'"
    width="50%"
    @close="handleClose"
  >
    <el-form :model="formData" label-width="80px">
      <el-form-item label="标题">
        <el-input v-model="title" placeholder="请输入标题" />
      </el-form-item>
      <el-form-item label="内容">
        <el-input
          v-model="content"
          type="textarea"
          :rows="4"
          placeholder="请输入内容"
        />
      </el-form-item>
    </el-form>
    <template #footer>
      <span class="dialog-footer">
        <el-button @click="closeDia">取消</el-button>
        <el-button type="primary" @click="sendNewsData">
          {{ type === 1 ? '确定' : '修改' }}
        </el-button>
      </span>
    </template>
  </el-dialog>
</template>

<script>
export default {
  emits: ['editNewsData', 'changeNewsData'],
  data() {
    return {
      type: 1,
      visible: false,
      id: null,
      title: '',
      content: '',
      formData: {
        title: '',
        content: ''
      }
    }
  },
  methods: {
    sendNewsData() {
      this.$emit(
        this.type == 1 ? 'editNewsData' : 'changeNewsData',
        { id: this.id, title: this.title, content: this.content }
      )
      this.closeDia()
    },
    closeDia() {
      this.resetForm()
      this.visible = false
    },
    handleClose() {
      this.resetForm()
    },
    resetForm() {
      this.id = null
      this.title = ''
      this.content = ''
      this.type = 1
      this.formData = {
        title: '',
        content: ''
      }
    }
  }
}
</script>

<style scoped>

</style>