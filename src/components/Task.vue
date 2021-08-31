<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
      {{ task.text }} <i class="fas fa-times" @click="onDelate(task.id)"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onDelate(id) {
      this.$emit("delete-task", id);
    },
  },
};
</script>

<style scoped>
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  border-left: 5px solid transparent;

  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid gold;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.fas {
  font-size: 20px;
  color: red;
  transition: all 0.2s;
}
.fas:hover {
  color: gold;
}
.fas:active {
  transform: scale(0.5);
}
</style>
