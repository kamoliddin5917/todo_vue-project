<template>
  <form class="add-form" @submit="onSubmit">
    <div class="form-control">
      <label> Note </label>
      <input type="text" v-model="text" name="text" placeholder="Add a note" />
    </div>

    <div class="form-control">
      <label> Date & time </label>
      <input
        type="text"
        v-model="day"
        name="day"
        placeholder="Add date and time"
      />
    </div>

    <div class="form-control form-control-check">
      <label>Mark</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input class="btn btn--block" type="submit" value="Save Note" />
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.text) {
        alert("Iltimos eslatma qo'shin!");
        return;
      }

      const newTask = {
        id: Math.floor(Math.random() * 100000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);

      this.text = "";
      this.day = "";
      this.reminder = false;
    },
  },
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}

.form-control {
  margin: 20px 0;
}

.form-control label {
  display: block;
}

.add-form input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}

.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.form-control-check label {
  flex: 1;
}

.form-control-check input {
  flex: 2;
  height: 20px;
  cursor: pointer;
}
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
  background-color: transparent;
  border: 1px solid #000;
}
.btn:active {
  transform: scale(0.7);
}
</style>
