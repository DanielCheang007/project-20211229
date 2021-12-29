<script setup>
import Todo from "@/models/todo.js";

const todoList = [];
todoList.push(new Todo("introduce to component"));
todoList.push(new Todo("introduce to Coposistion API"));

const appTitle = "Testing";
</script>

<template>
  <h1>{{ appTitle }} ({{ finishedTodoLength }} / {{ todoList.length }})</h1>

  <ul>
    <li
      v-for="(todo, idx) in todoList"
      :style="{ color: todo.color }"
      class="todo list-group-item"
      :class="{ 'todo--done': todo.done }"
    >
      <div>
        <input
          :id="'t_' + idx"
          type="checkbox"
          v-model="todo.done"
          class="form-check-input"
        />

        {{ todo.name }}

        <i> - {{ todo.date }} </i>

        <button @click="editTodo(todo)" class="btn btn-primary btn-sm">
          Edit
        </button>
        <button @click="delTodo(todo)" class="btn btn-danger btn-sm">
          Del
        </button>
      </div>
    </li>
  </ul>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
