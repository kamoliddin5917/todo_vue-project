<template>
  <button :style="{ background: color }" class="btn" @click="onClick()">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick() {
      this.$emit("toggle-add-task");
    },
  },
};
</script>

<style scoped>
.btn {
  display: inline-block;
  border: 1px solid transparent;
  outline: none;
  background-color: #000;
  color: #fff;
  font-size: 17px;
  font-weight: bold;
  padding: 5px 10px;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.4s;
  text-transform: capitalize;
}

.btn:hover {
  color: #222;
}
.btn:active {
  transform: scale(0.7);
}
</style>
