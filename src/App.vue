<template>
  <div>
    <h1>To-Do List</h1>
    <input v-model="newTask" placeholder="Add new task" />
    <button @click="addTask">Add</button>
    <ul>
      <li v-for="task in tasks" :key="task">{{ task }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tasks: [],
      newTask: "",
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim() !== "") {
        this.tasks.push(this.newTask.trim());
        this.newTask = "";
      }
    },
  },
};
</script>

<style>
h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

input {
  font-size: 1.2rem;
  padding: 0.5rem;
  margin-right: 0.5rem;
}

button {
  font-size: 1.2rem;
  padding: 0.5rem 1rem;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

li {
  margin-bottom: 0.5rem;
}
</style>
