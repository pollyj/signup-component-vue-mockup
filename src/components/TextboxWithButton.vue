<template>
  <div class="textbox-wrapper">
    <label :for="tag" class="textbox-label">{{ name }}</label>
    <div class="textbox-line-wrapper">
      <input :id="tag" :type="type" class="textbox-input" />
      <button v-on:click="togglePasswordDisplay" type="button" class="btn">{{btnText}}</button>
    </div>
    <p class="warning-text"></p>
  </div>
</template>

<script>
export default {
  name: "TextboxWithButton",
  data: function() {
    return {
      btnText: "Show",
      type: "password",
    };
  },
  props: {
    tag: String,
    name: String,
  },
  methods: {
    togglePasswordDisplay() {
      console.log(this.btnText);
      if (this.type === "text") {
        this.btnText = "Show";
        this.type = "password"
      } else {
        this.btnText = "Hide";
        this.type = "text";
      }
    }
  }
};
</script>

<style scoped>
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

.textbox-input {
  border-radius: 5px 0 0 5px;
  border: 1px solid #e4e2e2;
  height: 1.8rem;
  width: 100%;
  background-color: #f5f6f7;
  font-size: 1rem;
  padding: 5px;
}

.btn {
  background-color: #fff;
  height: 100%;
  padding: 0 8px;
  font-size: 0.8rem;
  color: #000;
  font-weight: normal;
  border: 1px solid #e4e2e2;
  border-radius: 0 5px 5px 0;
  cursor: pointer;
}
</style>