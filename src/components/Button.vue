<template>
  <div class="btn-wrapper">
    <button type="submit" class="btn" :form="id">{{btntext}}</button>
  </div>
</template>

<script>
export default {
  name: "Button",
  data() {
    return {};
  },
  props: {
    btntext: String,
    id: String
  }
};
</script>

<style>
.btn {
  width: fit-content;
  background-color: #f9a826;
  padding: 12px 24px;
  font-size: 1rem;
  color: #000;
  font-weight: bold;
  /* border: 2px solid #000000; */
  border: none;
  border-radius: 15px;
  /* cursor: pointer; */
  /* box-shadow: 5px 5px 5px #b3b3b3; */
}
</style>