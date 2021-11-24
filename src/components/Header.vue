<template>
  <header>
    <h1>{{ title }}</h1>
    <Button :color="btnColor" :text="btnText" @toggle-add="$emit('toggle-add')" />
  </header>
</template>

<script>
  import Button from './Button.vue'
  export default{
    name: "Header",
    components: {
      Button,
    },
    props: {
      title: String,
      showToggle: Boolean,
    },
    computed: {
      btnColor() {
        return this.showToggle ? "red" : "green";
      },
      btnText() {
        return this.showToggle ? "<i class='fas fa-times'></i>" : "Add Task";
      }
    },
  }
</script>

<style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
</style>