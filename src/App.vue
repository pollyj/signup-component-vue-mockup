<template>
  <div id="app">
    <SignUp />
  </div>
</template>

<script>
import SignUp from "./components/SignUp.vue";

export default {
  name: "App",
  components: {
    SignUp
  }
};
</script>

<style>
#app {
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* height: 100%;
  width: 100%; */
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #2c3e50;
  background-color: #fcfcfc;
}
</style>
