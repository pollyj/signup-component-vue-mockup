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
  display: block;
  height: 100vh;
  width: 100vw;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #2c3e50;
  background-color: #fcfcfc;
  font-size: 16px;
}

@media only screen and (min-width: 1024px) {
  #app {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>