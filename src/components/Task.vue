<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <div class="task__text">
      <p>{{ task.text }}</p>
      <i class="fas fa-times delete" @click="$emit('delete-task')"></i>
    </div>
    <div class="task__time">
      <p>{{ task.time }}</p>
      <i class="fas fa-bell set-reminder" title="Remind" @click="$emit('set-reminder')"></i>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Task",
    props: {
      task: Object,
    }
  }
</script>
<style scope>
  .delete:hover {
    color: red;
  }
  .task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
  }
  .task.reminder {
    border-left: 5px solid green;
  }
  .task__text {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .task__text p {
    font-size: 20px;
  }
  .task__time {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .task__time .set-reminder:hover {
    color: green;
  }
</style>