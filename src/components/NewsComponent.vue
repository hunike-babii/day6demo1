<template>
  <div class="news-container">
    <div class="header">
      <el-input
        v-model="search"
        placeholder="搜索"
        class="search-input"
        :prefix-icon="searchIcon"
        @input="$emit('searchNews', search)"
      >
        <template #append>
          <el-button @click="$emit('searchNews', search)">搜索</el-button>
        </template>
      </el-input>
      <el-button type="primary" @click="$emit('showAddDia', true)">
        添加新闻
      </el-button>
    </div>

    <el-table :data="list" style="width: 100%" border>
      <el-table-column type="index" label="序号" width="80" />
      <el-table-column prop="title" label="标题" />
      <el-table-column prop="content" label="内容" />
      <el-table-column label="操作" width="200">
        <template #default="scope">
          <el-button
            size="small"
            type="primary"
            @click="$emit('edit', scope.row)"
          >
            编辑
          </el-button>
          <el-popconfirm
            title="确定要删除这条新闻吗？"
            @confirm="$emit('del', scope.row)"
          >
            <template #reference>
              <el-button size="small" type="danger">删除</el-button>
            </template>
          </el-popconfirm>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import { Search } from '@element-plus/icons-vue'
import { markRaw } from 'vue'

export default {
  emits: ['searchNews', 'edit', 'del', 'showAddDia'],
  props: ['list'],
  data() {
    return {
      search: '',
      searchIcon: markRaw(Search)
    }
  }
}
</script>

<style scoped>
.news-container {
  padding: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.search-input {
  width: 300px;
}
</style>