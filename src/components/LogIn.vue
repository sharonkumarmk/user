<template>
  <div>
    <div v-if="!isAuthenticated" class="login_container">
      <div class="row">
        <div class="col">

          <input type="text" name="userName" placeholder="Username" required v-model="user.userName" />
          <input type="password" name="password" placeholder="Password" required v-model="user.password" />
          <button type="button" v-on:click="logIn()"> Log In </button>
        
        </div>
      </div>
    </div>
    <!--Component created for Home Page-->
    <Home v-if="isAuthenticated"></Home>
  </div>
</template>

<script>
import json from './../assets/credentials.json';
import Home from './Home.vue';
export default {
  name: 'LogIn',
  components: {
    Home
  },
  props: {
    
  },

  data() {
    return {
      user: {
        userName: '',
        password: ''
      },
      isAuthenticated: false,
      myJson: json,
    }
  },

  methods: {
    //Method to implememt Log in..
    logIn() {
      var data = this.user;
      if(data.userName == this.myJson.username && data.password == this.myJson.password) {
        this.isAuthenticated= true;
      } else {
        data.userName = '';
        data.password = '';
        alert("Inavlid Log In Credentails");
      }
    }
  }
}
</script>