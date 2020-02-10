<template>
  <div class="helloToDo">
    <HelloToDoInput @toDoAdded="addToDo" />
    <ul class="toDoList">
      <HelloToDoItem
        v-for="todo in todos"
        v-bind:key="todo.id"
        v-bind:todo="todo"
        @toDoCompleted="completeToDo"
      />
    </ul>
  </div>
</template>

<script>
import HelloToDoInput from './HelloToDoInput.vue'
import HelloToDoItem from './HelloToDoItem.vue'

export default {
  name: 'HelloToDo',
  components: {
    HelloToDoInput,
    HelloToDoItem
  },
  data: function () {
    return {
      todos: [],
      nextToDoId: 0
    }
  },
  methods: {
    addToDo: function (newToDo) {
      this.todos.push({
        id: this.nextToDoId,
        text: newToDo,
        isDone: false
      })
      this.nextToDoId++
    },
    removeToDo: function (toDoId) {
      this.todos.splice(this.todos.findIndex(({id}) => id === toDoId))
    },
    completeToDo: function (toDoId) {
      const indexToUpdate = this.todos.findIndex(({id}) => id === toDoId)
      this.todos.splice(indexToUpdate, 1, {
        ...this.todos[indexToUpdate],
        isDone: true
      })
    }
  }
}
</script>

<style scoped>
.helloToDo {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}

.helloToDo ul {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 300px;
}
</style>
