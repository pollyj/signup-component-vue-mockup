<template>
  <div class="signup-component">
    <div class="signup-img">
      <img src="../assets/undraw_team_spirit_hrr4.svg" alt height="200px" />
    </div>
    <div class="signup-grid-container">
      <!-- <form> -->
      <div class="signup-form-title">
        <h1 class="title-text">Sign Up Form</h1>
        <p class="required-text">All fields are required.</p>
      </div>
      <div class="signup-form-first-name">
        <Textbox tag="f-name" name="First Name" type="text" />
      </div>
      <div class="signup-form-last-name">
        <Textbox tag="l-name" name="Last Name" type="text" />
      </div>
      <div class="signup-form-email">
        <Textbox tag="email" name="Email Address" type="email" />
      </div>
      <div class="signup-form-password">
        <Textbox tag="password" name="Password" type="password" />
      </div>
      <div class="signup-form-confirm-password">
        <Textbox tag="c-password" name="Confirm Password" type="password" />
      </div>
      <div class="signup-form-terms">
        <p>Terms And Conditions</p>
      </div>
      <div class="signup-form-submit-btn">
        <Button btntext="Sign Up" />
      </div>
    </div>
    <!-- </form> -->
  </div>
</template>

<script>
import Textbox from "./Textbox.vue";
import Button from "./Button.vue";
// import Illustration from '../assets/undraw_team_spirit_hrr4.svg'

export default {
  name: "SignUp",
  data: function() {
    return {};
  },
  components: {
    Textbox,
    Button
    // Illustration
  },
  props: {
    msg: String
  }
};
</script>

<style scoped>
/* Smartphones (landscape) ----------- */
@media only screen and (min-width: 321px) {
  .signup-component {
    background-color: #fff;
    box-shadow: 10px 10px 8px #e4e4e4;
    border-radius: 25px;
    width: 90%;
    display: flex;
  }

  .signup-grid-container {
    display: grid;
    padding: 20px;
    margin: 10px;
    width: 100%;
    grid-template-columns: 1fr;
    grid-template-rows: 1.7fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
    gap: 1px 1px;
    grid-template-areas: "signup-form-title" "signup-form-first-name" "signup-form-last-name" "signup-form-email" "signup-form-password" "signup-form-confirm-password" "signup-form-terms" "signup-form-submit-btn";
  }

  div[class*="signup-form"] {
    display: flex;
    flex-direction: column;
    text-align: start;
  }

  .signup-img {
    display: none;
  }

  .signup-form-title {
    grid-area: signup-form-title;
    margin-bottom: 5px;
  }

  .title-text {
    border-bottom: 1px solid #F9A826;
    width: 100%;
    padding-bottom: 15px;
    margin-bottom: 0;
    color: #da8e14;
  }

  .required-text {
    font-style: italic;
    font-size: 0.9rem;
  }

  .signup-form-first-name {
    grid-area: signup-form-first-name;
  }

  .signup-form-last-name {
    grid-area: signup-form-last-name;
  }

  .signup-form-email {
    grid-area: signup-form-email;
  }

  .signup-form-password {
    grid-area: signup-form-password;
  }

  .signup-form-confirm-password {
    grid-area: signup-form-confirm-password;
  }

  .signup-form-terms {
    grid-area: signup-form-terms;
  }

  .signup-form-submit-btn {
    grid-area: signup-form-submit-btn;
    justify-content: center;
    align-items: center;
  }
}

/* iPads (portrait and landscape) ----------- */
@media only screen and (min-device-width: 768px) {
  .signup-component {
    display: flex;
  }

  .signup-grid-container {
    padding: 40px;
    width: 35vh;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto 1fr 1fr 1fr 1fr 1fr 1fr;
    gap: 1px 1px;
    grid-template-areas:
      "signup-form-title signup-form-title" "signup-form-first-name signup-form-last-name" "signup-form-email signup-form-email" "signup-form-password signup-form-password" "signup-form-confirm-password signup-form-confirm-password"
      "signup-form-terms signup-form-terms" "signup-form-submit-btn signup-form-submit-btn";
  }

  .signup-form-img {
    /* height: 100%;
      width: 100%; */
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .signup-form-title {
    grid-area: signup-form-title;
    margin-bottom: 25px;
  }
}

/* Desktops and laptops ----------- */
@media only screen and (min-width: 1224px) {
  /* STYLES GO HERE */
}
</style>