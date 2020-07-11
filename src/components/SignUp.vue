<template>
  <div class="signup-grid-container">
    <div class="signup-form-title">
      <h1>Sign Up Form</h1>
    </div>
    <div class="signup-form-first-name"></div>
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
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
  gap: 1px 1px;
  grid-template-areas: "signup-form-title signup-form-title" "signup-form-first-name signup-form-last-name" "signup-form-email signup-form-email" "signup-form-password signup-form-password" "signup-form-confirm-password signup-form-confirm-password" "signup-form-terms signup-form-terms" "signup-form-submit-btn signup-form-submit-btn";
}

.signup-form-title {
  grid-area: signup-form-title;
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
