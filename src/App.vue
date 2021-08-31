<template>
  <div class="container">
    <Header title="Track" />
    <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Tasks from "./components/Tasks";

export default {
  name: "App",
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(id) {
      console.log("task", id);
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "RealMadrid was created",
        day: "march 1st march 1989 at 2:20pm ",
        reminder: true,
      },
      {
        id: 2,
        text: "Barselona was created",
        day: "january 1st march 1990 at 2:20pm ",
        reminder: true,
      },
      {
        id: 3,
        text: "Chelsea was created",
        day: "july 1st march 1988 at 2:20pm ",
        reminder: true,
      },
    ];
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
