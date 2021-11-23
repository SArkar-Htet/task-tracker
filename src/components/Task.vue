<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']" @dblclick="$emit('set-reminder')">
    <div class="task__text">
      <p>{{ task.text }}</p>
      <i class="fas fa-times delete" @click="$emit('delete-task')"></i>
    </div>
    <p class="task__text">{{ task.time }}</p>
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
    cursor: pointer;
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
</style>