<template>
  <div id="app">
    <!--Component created for Log In Page-->
    <LogIn></LogIn>
  </div>
</template>

<script>
import LogIn from './components/LogIn.vue'

export default {
  name: 'App',
  components: {
    LogIn
  }
}
</script>

<style>
  @import "./css/style.css";
</style>
