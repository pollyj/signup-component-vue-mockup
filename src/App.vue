<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <SignUp/>
  </div>
</template>

<script>
import SignUp from './components/SignUp.vue'

export default {
  name: 'App',
  components: {
    SignUp
  }
}
</script>

<style>
#app {
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #2c3e50;
  background-color: #FCFCFC;
}
</style>
