<template>
    <div class="home_container">
        <table>
          <tr>
            <th v-for="header in headers" :key="header">{{header}}</th>
          </tr>
          <tr v-for="user in users" :key="user">
            <td v-for="header in headers" :key="header">{{user['user']}}</td>
          </tr>
        </table>
    </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
Vue.use(axios)

export default {
  name: 'Home',
  props: {
    
  },
  data() {
    var users = {};
    //Used Axios for making making http requests..
    axios.get('https://randomuser.me/api/0.8/?results=20')
      .then(response => 
        this.users = response.data.results);
    return {
      headers: ['Gender','Name', 'Email', 'User Name', 'Password', 'DOB', 'Phone'],
      users: users
    }
  }
}
</script>