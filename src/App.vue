<template>
  <header>
      <h2>To-do list</h2>
  </header>
  <article>
    <input v-model="newTask" placeholder="Enter task" type="text">
    <button class="add-button" @click="addTask">Add Task</button>
    <ul class="todo-list">
      <li class="li-task" v-for="(task, index) in tasks" :key="task">
        <input class="checkbox" type="checkbox">
        {{ task }}
        <button class="delete-button" @click="removeTask(index)">X</button>
      </li>
    </ul>
  </article>
</template>

<script>
  export default{
  data() {
    return {
      newTask: '',
      tasks: [],
    }
  },
  methods: {
    addTask() {
      this.tasks.push(this.newTask)
      this.newTask = ''
    },
    removeTask(index) {
      this.tasks.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
