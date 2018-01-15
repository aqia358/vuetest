<template>
  <li>
    {{ title }}
    <button v-on:click="$emit('remove')">X</button>
  </li>
</template>
<script>
  export default {
    name: 'todoItem',
    props: {
      title: {
        type: String,
        required: true
      }
    }
  }
</script>
