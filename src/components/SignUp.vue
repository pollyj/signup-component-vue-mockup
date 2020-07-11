<template>
  <div class="signup-grid-container">
    <div class="signup-form-title">
      <h1 class="title-text">Sign Up Form</h1>
      <p class="required-text">All fields are required.</p>
    </div>
    <div class="signup-form-first-name">
      <p>First Name</p>
    </div>
    <div class="signup-form-last-name">
      <p>Last Name</p>
    </div>
    <div class="signup-form-email">
      <p>Email Address</p>
    </div>
    <div class="signup-form-password">
      <p>Password</p>
    </div>
    <div class="signup-form-confirm-password">
      <p>Confirm Password</p>
    </div>
    <div class="signup-form-terms">
      <p>Terms And Conditions</p>
    </div>
    <div class="signup-form-submit-btn">
      <p>SIGN UP</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignUp",
  props: {
    msg: String
  }
};
</script>

<style scoped>
.signup-grid-container {
  background-color: #fff;
  box-shadow: 10px 10px 8px #e4e4e4;
  border-radius: 25px;
  display: grid;
  padding: 40px;
  width: 50vh;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1.5fr 1fr 1fr 1fr 1fr 1fr 1fr;
  gap: 1px 1px;
  grid-template-areas: "signup-form-title signup-form-title" "signup-form-first-name signup-form-last-name" "signup-form-email signup-form-email" "signup-form-password signup-form-password" "signup-form-confirm-password signup-form-confirm-password" "signup-form-terms signup-form-terms" "signup-form-submit-btn signup-form-submit-btn";
}

div[class*="signup-form"] {
  display: flex;
}

.signup-form-title {
  grid-area: signup-form-title;
  flex-direction: column;
  text-align: start;
}

.title-text {
  border-bottom: 1px solid rgb(219, 219, 219);
  width: 100%;
  padding-bottom: 15px;
  margin-bottom: 0;
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
}
</style>
