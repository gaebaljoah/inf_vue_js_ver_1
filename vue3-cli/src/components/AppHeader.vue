<template>
    <div>
        <h1>{{ apptitle }}</h1>
        <button @click="changeTitle">제목변경 버튼</button>
    </div>
</template>

<script>
    export default {
        props:['apptitle'],
        methods: {
            changeTitle() {
               this.$emit('change'); 
            }
        },
        
    }
</script>

<style scoped>

</style>