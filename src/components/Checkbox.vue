<template>
  <div class="checkbox-wrapper">
    <label :for="tag" class="checkbox-label">{{ name }}</label>
    <input :id="tag" type="checkbox" class="checkbox-input" />
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
    name: String
  }
};
</script>

<style scoped>
.checkbox-wrapper {
  display: flex;
  flex-direction: row-reverse;
  align-self: flex-start;
}

.checkbox-label {
  padding-bottom: 5px;
  color: #da8e14;
  font-weight: bold;
}

.checkbox-input {
  margin-right: 10px;
}
</style>