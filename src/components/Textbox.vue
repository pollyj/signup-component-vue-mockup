<template>
  <div class="textbox">
    <label :for="tag" class="textbox-label">{{ name }}</label>
    <input :id="tag" :type="type" class="textbox-input" />
  </div>
</template>

<script>
export default {
  name: "Textbox",
  props: {
    id: String,
    name: String,
    type: String
  }
};
</script>

<style scoped>
.textbox {
  display: flex;
  flex-direction: column;
}

.textbox-label {
  padding-bottom: 5px;
}

.textbox-input {
    border-radius: 5px;
    border: 1px solid #bbbbbb;
    height: 1.8rem;
}
</style>