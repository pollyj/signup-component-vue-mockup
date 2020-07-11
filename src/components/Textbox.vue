<template>
  <div class="textbox">
    <label :for="tag" class="textbox-label">{{ name }}</label>
    <input :id="tag" :type="type" class="textbox-input" />
  </div>
</template>

<script>
export default {
  name: "Textbox",
  data: function() {
    return {};
  },
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
  color: #da8e14;
  font-weight: bold;
}

.textbox-input {
  border-radius: 5px;
  border: 1px solid #e4e2e2;
  height: 1.8rem;
  background-color: #F5F6F7;
  font-size: 1rem;
  padding: 5px;
}
</style>