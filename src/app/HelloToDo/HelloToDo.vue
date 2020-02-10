<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>This is going to be a to do app.</p>
  </div>
</template>

<script>
export default {
  name: 'HelloToDo',
  props: {
    msg: String
  }
}
</script>

<style scoped>
p {
  font-size: 2em;
}
</style>
