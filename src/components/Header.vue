<template>
  <header>
    <h1>{{ title }}</h1>
    <Button text="Add Task" color="gold" />
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  components: {
    Button,
  },
  props: {
    title: String,
  },
};
</script>

<style>
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
  color: red;
}
</style>
