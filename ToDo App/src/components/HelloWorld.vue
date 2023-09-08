<script>
export default {
  data() {
    return {
      newTodo: '',
      todos: [],
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push({ text: this.newTodo, completed: false });
        this.newTodo = '';
      }
    },
    deleteCompleted() {
      this.todos = this.todos.filter((todo) => !todo.completed);
    },
  },
};
</script>

<template>
  <div class="hello">
    <h1>To do list</h1>
    <h3>Todo App</h3>
    <h5>using HTML, CSS and Vue 3</h5>
    <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new task">
    <button @click="addTodo">Add</button>
    <button @click="deleteCompleted">Delete Completed</button>
    <div v-for="(todo, index) in todos" :key="index">
      <input type="checkbox" v-model="todo.completed">
      {{ todo.text }}
    </div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
