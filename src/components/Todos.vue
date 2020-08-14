<template>
  <div>
    <!-- Loop through todos passed in as props. Remember to add key -->
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" />
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