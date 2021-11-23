<template>
  <div v-for="task in tasks">
    <Task :task="task" @delete-task="$emit('delete-task', task.id)" @set-reminder="$emit('set-reminder', task.id)" />
  </div>
</template>

<script>
  import Task from './Task.vue'
  export default {
    name: "Tasks",
    components: {
      Task,
    },
    props: {
      tasks: Array,
    },
  }
</script>