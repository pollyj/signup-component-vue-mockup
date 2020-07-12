<template>
  <div class="signup-component">
    <div class="signup-img-wrapper">
      <img class="signup-img" src="../assets/undraw_team_spirit_hrr4.svg" alt height="200px" />
    </div>

    <SignUpForm />
  </div>
</template>

<script>
import SignUpForm from './SignUpForm';

export default {
  name: "SignUpPage",
  data: function() {
    return {};
  },
  components: {
    SignUpForm
  },
  props: {
    msg: String
  },
  methods: {
    validateForm() {}
  }
};
</script>

<style scoped>
/* Smartphones ----------- */
@media screen and (min-width: 320px) {
  .signup-component {
    background-color: #fff;
    display: flex;
  }

  .signup-img-wrapper {
    display: none;
  }
}

/* iPads ----------- */
@media screen and (min-width: 768px) and (max-width: 1023px) {
  .signup-component {
    box-shadow: 10px 10px 8px #e4e4e4;
    border-radius: 25px;
    display: flex;
    margin: 0px auto;
    flex-direction: column;
    width: 80%;
    align-self: center;
  }

  .signup-img-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    background-color: rgb(248, 243, 239);
    border-radius: 25px 25px 0 0;
  }

  .signup-img {
    max-height: 200px;
    width: auto;
    padding: 15px 0;
  }

}

/* Desktops and laptops ----------- */
@media only screen and (min-width: 1024px) {
  .signup-component {
    display: flex;
    max-width: 65%;
    min-width: 1100px;
    align-self: center;
    box-shadow: 10px 10px 8px #e4e4e4;
    border-radius: 25px;
  }

  .signup-img-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 50%;
    background-color: rgb(248, 243, 239);
    border-radius: 25px 0 0 25px;
  }

  .signup-img {
    height: auto;
    width: 70%;
  }

  #signup-form {
    width: 50%;
  }

}
</style>