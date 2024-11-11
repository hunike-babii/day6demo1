<template>
    <div>
        <div v-if="visible">
            <input type="text" v-model="title" placeholder="标题" />
            <input type="text" v-model="content" placeholder="内容" />
            <button @click="sendNewsData">确定</button>
            <button @click="closeDia">取消</button>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                type: 1,
                visible: false,
                id: null,
                title: '',
                content: ''
            }
        },
        methods: {
            sendNewsData() {
                this.$emit('sendNewsData', {title: this.title, content: this.content})
                this.closeDia()
            },
            closeDia() {
                this.visible = false
                this.id = -1
                this.title = ''
                this.content = ''
                this.type = 1
            }
        }
    }
</script>

<style scoped>

</style>