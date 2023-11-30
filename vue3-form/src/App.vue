<template>
  <form action="" @submit.prevent="submitForm">
    <div>
      <label for="userId">ID:</label>
      <input v-model="username" id="userId" type="text"/>
    </div>
    <div>
      <label for="password">PW:</label>
      <input v-model="password" id="password" type="text"/>
    </div>
    <button type="submit">로그인</button>
  </form>
</template>

<script>

  import axios from 'axios'
  import { ref } from 'vue';

  export default {

    //data
    setup(){
      var username = ref(''); // <= 아래 data(){return{ username = '' }} 한 것과 같음
      var password = ref('');

    //methods
      var submitForm = () => {
        axios.post('https://jsonplaceholder.typicode.com/users/', {
          username1 : username.value, //ref로 지정한 키의 value 값 가져오기
          password1: password.value
        }).then(res => {
          console.log(res);
        })
      }

      return { username, password, submitForm } //<= return한 값들은 options API에서 사용가능
    },


    // data() {
    //   return {
    //     //username: '',
    //     //password: '',
    //   }
    // },
    // methods: {
    //   submitForm() { //event.preventDefault(); // <- 이렇게 직접적으로 제어 안하고 template에서 submit.prevent로 처리할 수 있다.

    //     const data = {
    //       username1: this.username, // username1 -> key값  username -> form data안의 v-model로 바인딩 된 값 v-model로 바인딩 해야 this로 접근 가능
    //       password1: this.password
    //     }

    //     axios.post('https://jsonplaceholder.typicode.com/users/', data)
    //     .then(res => {
    //       console.log(res);
    //     });
    //   }
    // },
  }
</script>

<style scoped>

</style>