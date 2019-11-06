<template>
  <div id="todolist">
    <div class="todo-input">
      <form @submit.prevent="addTodo">
        <input type="text" v-model="todoInput" placeholder="insert item" />
        <button type="submit">Add</button>
      </form>
      <ul>
        <li v-for="todo in todos" v-bind:key="todo.id">
          <input type="checkbox" v-model="todo.checked" />
          <span :class="{done: todo.checked}">{{todo.title}}</span>
          <button @click="removeTodo(todo)">X</button>
        </li>
      </ul>
      <button @click="markAll">Mark all</button>
      <button @click="unMarkAll">Unmark all</button>
      <button @click="removeAll">Remove all</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todolist",

  data() {
    return {
      todoInput: "",
      todos: []
    };
  },
  methods: {
    addTodo() {
      this.todos.push({ title: this.todoInput, checked: false });
      this.todoInput = "";
      window.console.log(this.todos);
    },
    removeTodo(todo) {
      const index = this.todos.indexOf(todo);
      this.todos.splice(index, 1);
    },

    markAll() {
      this.todos.forEach(todo => {
        todo.checked = true;
      });
    },

    unMarkAll() {
      this.todos.forEach(todo => {
        todo.checked = false;
      });
    },

    removeAll() {
      this.todos = [];
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.done {
  text-decoration: line-through;
}
input[type="text"] {
  border: 1px solid gray;
}
ul {
  list-style: none;
  padding: 0px;
}
li {
  display: flex;
  justify-content: space-between;
  border: 1px solid gray;
  padding: 30px;
}
</style>
