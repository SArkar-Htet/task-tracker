<template>
  <div>
    <form @submit.prevent="onSubmit" class="add-form">
      <div class="form-control">
        <label>Task</label>
        <input type="text" v-model="text" name="text" placeholder="Add Task" />
      </div>
      <div class="form-control">
        <label>Day & Time</label>
        <input
          type="text"
          v-model="time"
          name="time"
          placeholder="Add Day & Time"
        />
      </div>
      <div class="form-control form-control-check">
        <label>Set Reminder</label>
        <input type="checkbox" v-model="reminder" name="reminder" />
      </div>

      <input type="submit" value="Save Task" class="btn btn-block" />
    </form>
  </div>
</template>

<script>
  export default {
    name: "AddTask",
    data() {
      return {
        text: "",
        time: "",
        reminder: false,
      }
    },
    methods: {
      onSubmit() {
        if (!this.text) {
          alert("Please fill task field");
          return;
        }
        if (!this.time) {
          alert("Please fill day & time field");
          return;
        }

        const newTask = {
          text: this.text,
          time: this.time,
          reminder: this.reminder,
        }
        
        this.$emit("add-task", newTask);

        this.text = "";
        this.time = "";
        this.reminder = false;
      }
    }
  }
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
.form-control input {
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
}
</style>