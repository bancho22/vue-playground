<template>
  <input type="text" v-model="inputValue" @keyup.enter="onSubmit" placeholder="What is to be done?" />
</template>

<script>
export default {
  name: 'HelloToDoInput',
  props: [],
  data: function () {
    return {
      inputValue: ''
    }
  },
  methods: {
    onSubmit: function () {
      if (this.inputValue.length > 0)
        this.$emit('toDoAdded', this.inputValue)
        this.inputValue = ''
      }
  }
}
</script>

<style scoped>
input {
  height: 30px;
  width: 300px;
  padding: 16px 16px 16px 60px;
  font-size: 1.3em;
  background-color: #ffffff5c;
  box-shadow: inset 0 -2px 1px rgba(0,0,0,0.03);
  border: 0;
  outline: 0;
}

input::placeholder {
  font-weight: 500;
  font-style: italic;
}
</style>
