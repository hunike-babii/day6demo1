<template>
    <div>
        <div class="header">
            <div>
                <input type="text" placeholder="搜索" />
            </div>
            <div>
                <button @click="$emit('showAddDia',true)">添加</button>
            </div>
        </div>
        <table>
            <tr>
                <th>序号</th>
                <th>标题</th>
                <th>内容</th>
                <th>操作</th>
            </tr>
            <tr v-for="(item, index) in list" :key="item.id">
                <td>{{ index + 1 }}</td>
                <td>{{ item.title }}</td>
                <td>{{ item.content }}</td>
                <td>
                    <button @click="edit(item)">编辑</button>
                    <button @click="del(item)">删除</button>
                </td>
            </tr>
        </table>
    </div>
</template>

<script>
    export default {
        props: ['list'],
        data() {
            return {
                
            }
        }
    }
</script>

<style scoped>
    .header {
        display: flex;
        justify-content: space-between;
    }
    table {
        width: 100%;
    }
    th {
        border: 1px solid #000;
    }
    td {
        border: 1px solid #000;
    }
</style>