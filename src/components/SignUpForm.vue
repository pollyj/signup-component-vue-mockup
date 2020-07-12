<template>
  <form id="signup-form" @submit="validateForm">
    <div class="signup-grid-container">
      <div class="signup-form-title">
        <h1 class="title-text">Create Your Account</h1>
        <p class="required-text">All fields are required.</p>
      </div>
      <div class="signup-form-first-name textbox-wrapper">
        <label for="f-name" class="textbox-label">First Name</label>
        <input id="f-name" type="text" class="textbox-input" />
      </div>
      <div class="signup-form-last-name textbox-wrapper">
        <label for="l-name" class="textbox-label">Last Name</label>
        <input id="l-name" type="text" class="textbox-input" />
      </div>
      <div class="signup-form-email textbox-wrapper">
        <label for="email" class="textbox-label">Email Address</label>
        <input id="email" type="email" class="textbox-input" />
      </div>
      <div class="signup-form-password textbox-wrapper">
          <label for="password" class="textbox-label">Password</label>
          <div class="textbox-line-wrapper">
            <input id="password" :type="passwordInputType" class="textbox-btn-input" />
            <button
              v-on:click="togglePasswordDisplay('password')"
              type="button"
              class="textbox-btn"
            >{{passwordBtnText}}</button>
          </div>
        <div class="help-text">
          <ul>
            <li class="pw-req-1">- Minimum 12 characters</li>
            <li
              class="pw-req-2"
            >- Must contain at least 2 upper case letters, 2 numbers, and 2 symbols</li>
          </ul>
        </div>
        <p class="warning-text-password"></p>
      </div>

      <div class="signup-form-confirm-password">
        <div class="textbox-wrapper">
          <label for="c-password" class="textbox-label">Confirm Password</label>
          <div class="textbox-line-wrapper">
            <input id="c-password" :type="confirmInputType" class="textbox-btn-input" />
            <button
              v-on:click="togglePasswordDisplay('confirm')"
              type="button"
              class="textbox-btn"
            >{{confirmBtnText}}</button>
          </div>
        </div>
        <p class="warning-text-confirm-password"></p>
      </div>
      <div class="signup-form-terms">
        <div class="checkbox-wrapper">
          <label for="terms" class="checkbox-label">Terms and Conditions</label>
          <div class="checkbox-line-wrapper">
            <input id="terms" type="checkbox" class="checkbox-input" />
            <p class="helper-text">I agree to the terms and conditions</p>
          </div>
        </div>
        <p class="warning-text-terms"></p>
      </div>
      <div class="signup-form-submit-btn">
        <div class="btn-wrapper">
          <button type="submit" class="btn" form="signup-form">Sign Up</button>
        </div>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "SignUpForm",
  data: function() {
    return {
      passwordInputType: "password",
      passwordBtnText: "Show",
      confirmInputType: "password",
      confirmBtnText: "Show",
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
    validateForm() {}
  }
};
</script>

<style scoped>
/* Smartphones (landscape) ----------- */
@media screen and (min-width: 321px) {
  .signup-grid-container {
    display: grid;
    padding: 20px;
    margin: 10px;
    grid-template-columns: 1fr;
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

  ul {
    padding: 0;
  }

  .help-text {
    font-size: 0.8rem;
  }

  p[class*="warning-text-"] {
    line-height: 1rem;
    height: 20px;
    color: red;
    font-weight: bold;
    font-size: 0.8rem;
  }

  /* TEXTBOX STYLES */

  .textbox-wrapper {
    display: flex;
    flex-direction: column;
     margin-bottom: 15px;
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
    /* height: 100%; */
    min-width: 60px;
    padding: 0 8px;
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
  }
}

/* iPads (portrait and landscape) ----------- */
@media screen and (min-width: 768px) {
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
    /* width: 100%; */
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto auto auto auto auto auto auto;
    gap: 1px 20px;
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