<template>
    <form @submit="submitForm">
      <div>
        <label for="username">id : </label>        
        <!-- v-model : 사용자의 입력값을 data에 저장 -->
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
export default {
  data: function() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    submitForm: function(e) {
      e.preventDefault();
      console.log(this.username, this.password);
      
    }
  }
}
</script>

<style>

</style>     