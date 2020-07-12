<template>
  <div id="app">
    <SignUpPage />
  </div>
</template>

<script>
import SignUpPage from "./components/SignUpPage.vue";

export default {
  name: "App",
  components: {
    SignUpPage
  }
};
</script>

<style>
#app {
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  height: 100vh;
  width: 100vw;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #2c3e50;
  background-color: #fcfcfc;
}
</style>
