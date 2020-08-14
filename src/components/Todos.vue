<template>
  <div>
    <!-- Loop through todos passed in as props. Remember to add key -->
    <div v-bind:key="todo.id" v-for="todo in todos">
      <!-- Binding todo data to TodoItem attribute as well as catch and re-emit delete event to App -->
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"], //Receive props from parent (App.vue) as array
};
</script>

<style scoped>
</style>