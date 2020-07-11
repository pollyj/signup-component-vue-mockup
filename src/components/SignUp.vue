<template>
  <div class="signup-component">
    <div class="signup-img-wrapper">
      <img class="signup-img" src="../assets/undraw_team_spirit_hrr4.svg" alt height="200px" />
    </div>
    <form id="signup-form">
      <div class="signup-grid-container">
        <div class="signup-form-title">
          <h1 class="title-text">Create Your Account</h1>
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
          <Checkbox tag="terms" name="Terms and Conditions" />
          <p>
            <span class="small-text">
              Creating an account means that you agree to our
              <a href="/">terms and conditions</a>.
            </span>
          </p>
        </div>
        <div class="signup-form-submit-btn">
          <Button btntext="Sign Up" form="signup-form" />
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import Textbox from "./Textbox.vue";
import Button from "./Button.vue";
import Checkbox from "./Checkbox.vue";

export default {
  name: "SignUp",
  data: function() {
    return {};
  },
  components: {
    Textbox,
    Button,
    Checkbox
  },
  props: {
    msg: String
  }
};
</script>

<style scoped>
/* Smartphones (landscape) ----------- */
@media screen and (min-width: 321px) {
  .signup-component {
    background-color: #fff;
    display: flex;
  }

  .signup-grid-container {
    display: grid;
    padding: 20px;
    margin: 10px;
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

  .signup-img-wrapper {
    display: none;
  }

  .signup-form-title {
    grid-area: signup-form-title;
    margin-bottom: 5px;
  }

  .title-text {
    border-bottom: 1px solid #f9a826;
    width: 100%;
    padding-bottom: 15px;
    margin-bottom: 0;
    color: #da8e14;
  }

  .required-text {
    font-style: italic;
    font-size: 0.9rem;
    margin-top: 15px;
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

  .small-text {
    font-size: 0.8rem;
  }
}

/* iPads (portrait and landscape) ----------- */
@media screen and (min-width: 768px) and (max-width: 1024px) {
  .signup-component {
    box-shadow: 10px 10px 8px #e4e4e4;
    border-radius: 25px;
    display: flex;
    margin-top: 20px;
    flex-direction: column;
    width: 80%;
    align-self: center;
  }

  .signup-grid-container {
    padding: 20px 40px;
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

  .signup-form-title {
    grid-area: signup-form-title;
    margin-bottom: 25px;
  }
}

/* Desktops and laptops ----------- */
@media only screen and (min-width: 1024px) {
  .signup-component {
    display: flex;
    width: 65%;
    align-self: center;
    box-shadow: 10px 10px 8px #e4e4e4;
    border-radius: 25px;
  }

  .signup-grid-container {
    padding: 40px;
    width: 50%;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto 1fr 1fr 1fr 1fr 1fr 1fr;
    gap: 1px 10px;
    grid-template-areas:
      "signup-form-title signup-form-title" "signup-form-first-name signup-form-last-name" "signup-form-email signup-form-email" "signup-form-password signup-form-password" "signup-form-confirm-password signup-form-confirm-password"
      "signup-form-terms signup-form-terms" "signup-form-submit-btn signup-form-submit-btn";
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

  .signup-form-title {
    grid-area: signup-form-title;
    margin-bottom: 25px;
  }
}
</style>