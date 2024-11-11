<template>
    <div>
        <div v-if="type === 1">
            <h1>Add Edit Dia</h1>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                type: 1,
                visible: false
            }
        }
    }
</script>

<style scoped>

</style>