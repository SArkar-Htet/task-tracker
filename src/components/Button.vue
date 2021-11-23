<template>
  <button class="btn" :style="{backgroundColor: color}" @click="$emit('toggle-add')"><span v-html="text"></span></button>
</template>

<script>
  export default{
    name: "Button",
    props: {
      color: String,
      text: String,
    }
  }
</script>