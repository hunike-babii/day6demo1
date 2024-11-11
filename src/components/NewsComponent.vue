<template>
    <div>
        <div class="header">
            <div>
                <input type="text" v-model="search" placeholder="搜索" />
                <button @click="$emit('searchNews',search)">搜索</button>
            </div>
            <div>
                <button @click="$emit('showAddDia',true)">添加</button>
            </div>
        </div>
        <table>
            <thead> 
                <tr>
                    <th>序号</th>
                    <th>标题</th>
                    <th>内容</th>
                    <th>操作</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, index) in list" :key="item.id">
                    <td>{{ index + 1 }}</td>
                    <td>{{ item.title }}</td>
                    <td>{{ item.content }}</td>
                    <td>
                        <button @click="$emit('edit',item)">编辑</button>
                        <button @click="$emit('del',item)">删除</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        props: ['list'],
        data() {
            return {
                search: ''
            }
        }
    }
</script>

<style scoped>
    .header {
        display: flex;
        justify-content: space-between;
        margin-bottom: 10px;
    }
    table {
        width: 80%;
        margin: 0 auto;
        border: 1px solid #000;
    }
    th {
        border: 1px solid #000;
    }
    td {
        border: 1px solid #000;
    }
</style>