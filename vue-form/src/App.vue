<template>
  <div>
    <form v-on:submit.prevent="subnitForm">
      <div>
        <label for="username">id: </label>
        <input type="text" id="username" v-model="username">
      </div>
      <div>
        <label for="password">pw: </label>
        <input type="password" id="password" v-model="password">
      </div>
      <button type="submit">Login</button>
    </form>

  </div>
</template>

<script>
import axios from 'axios';

export default {
  data: function() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    subnitForm: function(){
      //event.preventDefault();
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password
      }
      axios.post(url, data)
        .then( function(response){
          console.log(response);
        })
        .catch( function(error){
          console.log(error);
        })
    }
  }
}
</script>

<style>

</style>