<template>
  <AppHeader 
    v-bind:apptitle="message"
    v-on:change="changMessage"
  >
  </AppHeader>
  <button @click="showAlert">경고</button>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
export default {
  components:{AppHeader},
  data() {
    return {
      message: 'hello'
    }
  },methods: {
    showAlert() {
      alert("hello")
    },
    changMessage() {
      this.message="제목변경 컴포넌트"
    }
  },
  
}
</script>

<style scoped>

</style>