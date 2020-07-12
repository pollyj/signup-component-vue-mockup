<template>
  <form id="signup-form" @submit.prevent="validateForm">
    <div class="signup-grid-container">
      <div class="signup-form-title">
        <h1 class="title-text">Create Your Account</h1>
        <p class="required-text">All fields are required.</p>
      </div>

      <div class="signup-form-first-name textbox-wrapper">
        <label for="f-name" class="textbox-label">First Name</label>
        <input id="f-name" v-model="fName" type="text" class="textbox-input" />
        <p class="warning-text-password">{{fNameError ? fNameError : ""}}</p>
      </div>

      <div class="signup-form-last-name textbox-wrapper">
        <label for="l-name" class="textbox-label">Last Name</label>
        <input id="l-name" v-model="lName" type="text" class="textbox-input" />
        <p class="warning-text-password">{{lNameError ? lNameError : ""}}</p>
      </div>

      <div class="signup-form-email textbox-wrapper">
        <label for="email" class="textbox-label">Email Address</label>
        <input id="email" v-model="email" type="email" class="textbox-input" />
        <p class="warning-text-password">{{emailError ? emailError : ""}}</p>
      </div>

      <div class="signup-form-password textbox-wrapper">
        <label for="password" class="textbox-label">Password</label>
        <div class="textbox-line-wrapper">
          <input
            id="password"
            v-model="password"
            :type="passwordInputType"
            class="textbox-btn-input"
          />
          <button
            v-on:click="togglePasswordDisplay('password')"
            type="button"
            class="textbox-btn"
          >{{passwordBtnText}}</button>
        </div>
        <div class="help-text">
          <ul>
            <li
              v-bind:class="[helpText1 ? '' : 'warning-text-req1']"
              class="pw-req-1"
            >- Minimum 12 characters</li>
            <li
              v-bind:class="[helpText2 ? '' : 'warning-text-req2']"
              class="pw-req-2"
            >- Must contain at least 2 upper case letters, 2 numbers, and 2 symbols</li>
          </ul>
        </div>
        <div class="warning-text-password">{{passwordError ? passwordError : ""}}</div>
      </div>

      <div class="signup-form-confirm-password">
        <div class="textbox-wrapper">
          <label for="c-password" class="textbox-label">Confirm Password</label>
          <div class="textbox-line-wrapper">
            <input
              id="c-password"
              v-model="confirmPassword"
              :type="confirmInputType"
              class="textbox-btn-input"
            />
            <button
              v-on:click="togglePasswordDisplay('confirm')"
              type="button"
              class="textbox-btn"
            >{{confirmBtnText}}</button>
          </div>
        </div>
        <p class="warning-text-password">{{confirmPasswordError ? confirmPasswordError : ""}}</p>
      </div>

      <div class="signup-form-terms">
        <div class="checkbox-wrapper">
          <label for="terms" class="checkbox-label">Terms and Conditions</label>
          <div class="checkbox-line-wrapper">
            <input id="terms" v-model="terms" type="checkbox" class="checkbox-input" />
            <p class="helper-text">I agree to the terms and conditions</p>
          </div>
        </div>
        <p class="warning-text-password">{{termsError ? termsError : ""}}</p>
      </div>
      <div class="signup-form-submit-btn btn-wrapper">
        <button type="submit" class="btn" form="signup-form">Sign Up</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "SignUpForm",
  data: function() {
    return {
      fName: null,
      fNameError: null,
      lName: null,
      lNameError: null,
      email: null,
      emailError: null,
      password: null,
      passwordError: null,
      confirmPassword: null,
      confirmPasswordError: null,
      terms: false,
      termsError: false,
      passwordInputType: "password",
      passwordBtnText: "Show",
      confirmInputType: "password",
      confirmBtnText: "Show",
      helpText1: true,
      helpText2: true
    };
  },
  methods: {
    togglePasswordDisplay(type) {
      if (type === "password") {
        if (this.passwordInputType === "text") {
          this.passwordBtnText = "Show";
          this.passwordInputType = "password";
        } else {
          this.passwordBtnText = "Hide";
          this.passwordInputType = "text";
        }
      } else if (type === "confirm") {
        if (this.confirmInputType === "text") {
          this.confirmBtnText = "Show";
          this.confirmInputType = "password";
        } else {
          this.confirmBtnText = "Hide";
          this.confirmInputType = "text";
        }
      }
    },
    validateForm() {
      //reset previous validation errors
      this.fNameError = null;
      this.lNameError = null;
      this.emailError = null;
      this.termsError = null;
      this.passwordError = null;
      this.helpText1 = true;
      this.helpText2 = true;

      if (!this.fName) {
        this.fNameError = "Please enter a first name.";
      }

      if (!this.lName) {
        this.lNameError = "Please enter a last name.";
      }

      this.validateEmail(this.email);
      this.validatePassword(this.password);

      if (!this.terms) {
        this.termsError = "Please check the terms and conditions.";
      }
    },
    validateEmail(email) {
      this.emailError = null;

      if (!this.email) {
        this.emailError = "Please enter an email.";
        return false;
      } else if (
        !/^\w+([\\.-]?\w+)*@\w+([\\.-]?\w+)*(\.\w{2,3})+$/.test(email)
      ) {
        this.emailError = "Please enter a valid email.";
        return false;
      }
      return true;
    },
    validatePassword(string) {
      if (!string) {
        this.passwordError = "Please enter a password.";
        return false;
      } else if (string.length < 12) {
        this.passwordError = null;
        this.helpText1 = false;
        return false;
      }

      let map = {
        number: 0,
        upper: 0,
        symbol: 0
      };
      for (let i = 0; i < string.length; i++) {
        if (Number.isInteger(Number(string.charAt(i)))) {
          map.number += 1;
        } else if (string[i].match(/[A-Z]/)) {
          map.upper += 1;
        } else if (!string[i].match(/[a-z]/i)) {
          map.symbol += 1;
        }
      }

      if (map.number >= 2 && map.upper >= 2 && map.symbol >= 2) {
        if (this.password === this.confirmPassword) {
          this.confirmPasswordError = null;
          return true;
        } else {
          this.confirmPasswordError = "Passwords don't match.";
          return false;
        }
      } else {
        this.helpText2 = false;
        return false;
      }
    }
  }
};
</script>

<style scoped>
/* Smartphones (landscape) ----------- */
@media screen and (min-width: 320px) {
  .signup-grid-container {
    display: grid;
    padding: 20px;
    margin: 10px;
    grid-template-columns: auto;
    grid-template-rows: auto auto auto auto auto auto auto auto;
    gap: 1px 1px;
    grid-template-areas: "signup-form-title" "signup-form-first-name" "signup-form-last-name" "signup-form-email" "signup-form-password" "signup-form-confirm-password" "signup-form-terms" "signup-form-submit-btn";
  }

  div[class*="signup-form-"] {
    display: flex;
    flex-direction: column;
    text-align: start;
  }

  .signup-form-title {
    grid-area: signup-form-title;
    /* margin-top: 20px; */
  }

  .title-text {
    border-bottom: 1px solid #f9a826;
    width: 100%;
    padding-bottom: 5px;
    margin-bottom: 0;
    color: #da8e14;
  }

  .required-text {
    font-style: italic;
    font-size: 0.9rem;
    margin: 15px 0;
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

  ul {
    padding: 0;
  }

  .help-text {
    font-size: 0.8rem;
    line-height: 0.9rem;
    margin: -5px 0;
  }

  [class*="warning-text"] {
    min-height: 0.9rem;
    color: red;
    font-weight: bold;
    font-size: 0.8rem;
  }

  /* TEXTBOX STYLES */

  .textbox-wrapper {
    display: flex;
    flex-direction: column;
    margin-bottom: 5px;
  }

  .textbox-label {
    padding-bottom: 5px;
    color: #da8e14;
    font-weight: bold;
  }

  .textbox-input {
    border-radius: 5px;
    border: 1px solid #e4e2e2;
    height: 1.8rem;
    background-color: #f5f6f7;
    font-size: 1rem;
    padding: 5px;
    margin-bottom: 5px;
  }

  /* TEXTBOX WITH BUTTON STYLES */

  .textbox-wrapper {
    display: flex;
    flex-direction: column;
  }

  .textbox-line-wrapper {
    display: flex;
  }

  .textbox-label {
    padding-bottom: 5px;
    color: #da8e14;
    font-weight: bold;
  }

  .textbox-btn-input {
    border-radius: 5px 0 0 5px;
    border: 1px solid #e4e2e2;
    height: 1.8rem;
    width: 100%;
    background-color: #f5f6f7;
    font-size: 1rem;
    padding: 5px;
  }

  .textbox-btn {
    background-color: #fff;
    min-width: 60px;
    padding: 0 5px;
    font-size: 0.8rem;
    border: 1px solid #e4e2e2;
    border-radius: 0 5px 5px 0;
    cursor: pointer;
  }

  /* CHECKBOX STYLES */

  .checkbox-wrapper {
    display: flex;
    flex-direction: column;
    align-self: flex-start;
  }

  .checkbox-label {
    padding-bottom: 5px;
    color: #da8e14;
    font-weight: bold;
  }

  .checkbox-line-wrapper {
    display: flex;
    padding: 5px 0;
    margin-bottom: 5px;
  }

  .checkbox-input {
    margin: 1px 10px 0 0;
    align-self: flex-start;
  }

  .helper-text {
    font-size: 0.9rem;
  }

  /* BUTTON STYLES */
  .btn {
    width: fit-content;
    background-color: #f9a826;
    padding: 12px 24px;
    font-size: 1rem;
    color: #000;
    font-weight: bold;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    margin-top: 15px;
  }
}

/* iPads (portrait and landscape) ----------- */
@media screen and (min-width: 768px) and (max-width: 1023px) {

  .signup-grid-container {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px 40px;
  }

  .signup-form-title {
    grid-area: signup-form-title;
    margin-bottom: 25px;
  }
}

/* Desktops and laptops ----------- */
@media only screen and (min-width: 1024px) {
  .signup-grid-container {
    padding: 20px 40px;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto auto auto auto auto auto auto;
    gap: 1px 20px;
    grid-template-areas:
      "signup-form-title signup-form-title" "signup-form-first-name signup-form-last-name" "signup-form-email signup-form-email" "signup-form-password signup-form-password" "signup-form-confirm-password signup-form-confirm-password"
      "signup-form-terms signup-form-terms" "signup-form-submit-btn signup-form-submit-btn";
  }

  .signup-form-title {
    grid-area: signup-form-title;
    margin-bottom: 25px;
  }
}
</style>