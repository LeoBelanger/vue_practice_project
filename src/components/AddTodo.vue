<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add Todo..."
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
//import { v4 as uuidv4 } from "uuid";
//No longer need since jsonplaceholder provides id
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault(); //Prevent the form from actually submitting
      const newTodo = {
        title: this.title,
        completed: false,
      };
      this.$emit("add-todo", newTodo); //Emit new todo to App.vue
      this.title = ""; //Clears the input after submitting
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}
</style>
