<template>
<!-- form 자체의 submit event 제어, button에 이벤트를 등록하지 않는다 !! -->
<!-- prevent :  event의 기본동작을 제어할 수 있다 -->
    <form @submit.prevent="submitForm">
      <div>
        <label for="username">id : </label>        
        <!-- v-model : 사용자의 입력값을 data에 저장 -->
        <!-- 실시간 데이터바인딩  -->
        <input id="username" type="text" v-model="username">
      </div>
      <div>
        <label for="password">pw : </label>        
        <input id="password" type="text" v-model="password">
      </div>
      <button type="submit">login</button>
    </form>
</template>

<script>
import axios from 'axios';

export default {
  data: function() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    submitForm: function() {
      console.log(this.username, this.password);
      // browser에서 server로 데이터를 주고 받기 위한 라이브러리
      // post : 데이터를 생성 및 저장할 때 생성하는 method
      const url = 'https://jsonplaceholder.typicode.com/users';
      const data = {
        username : this.username,
        password : this.password
      }
      axios.post(url, data)
        .then(function(res) {
            console.log(res);
        })
        .catch(function(err) {
          console.log(err);
        });
      
    }
  }
}
</script>

<style>

</style>     