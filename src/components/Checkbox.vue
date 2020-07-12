<template>
  <div class="checkbox-wrapper">
    <label :for="tag" class="checkbox-label">{{ name }}</label>
    <div class="checkbox-line-wrapper">
      <input :id="tag" type="checkbox" class="checkbox-input" />
      <p class="helper-text" v-if="msg">{{ msg }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Button",
  data() {
    return {};
  },
  props: {
    tag: String,
    name: String,
    msg: String
  }
};
</script>

<style scoped>
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
</style>