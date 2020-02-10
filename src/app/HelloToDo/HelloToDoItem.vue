<template>
  <li :class="{done: todo.isDone}" @click.once="$emit('toDoCompleted', todo.id)">{{ todo.text }}</li>
</template>

<script>
export default {
  name: 'HelloToDoItem',
  props: {
    todo: {
      id: String,
      text: String,
      isDone: Boolean
    }
  }
}
</script>

<style scoped>
li {
  font-size: 1.5em;
  padding: 5px 0;
  cursor: pointer;
}

.done {
  color: #03aa51;
  cursor: auto;
  text-decoration-line: line-through;
}
</style>
