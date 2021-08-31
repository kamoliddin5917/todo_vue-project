<template>
  <div class="container">
    <Header title="Track" />
  </div>
</template>

<script>
import Header from "./components/Header";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  max-width: 800px;
  padding: 10px 15px;
  margin-left: auto;
  margin-right: auto;
  border: 1px solid black;
}
</style>
