// App.vue
<template>
  <div id="app">
    <ToDos v-bind:todoEntries="todoEntries" @delete-todo-event="deleteTodDoItem" />
    <AddToDoButton @add-todo-event="addToDoItem" />
  </div>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
</template>

<script>
import ToDos from './components/ToDos'
import AddToDoButton from "@/components/addToDoButton.vue";

export default {
  name: 'App',
  components: {
    ToDos,
    AddToDoButton
  },
  data() {
    return {
      todoEntries: [
        {
          id: 1,
          title: 'Gather information',
          completed: false
        },
        {
          id: 2,
          title: 'Create a test project',
          completed: false
        },
        {
          id: 3,
          title: 'Write a blog entry',
          completed: false
        },
      ],
    }
  },

  methods: {
    addToDoItem(newToDoItem) {
      this.todoEntries.push(newToDoItem);
    },

    deleteTodDoItem(itemId) {
      this.todoEntries = this.todoEntries.filter(item => item.id !== itemId);
    }
  },
}
</script>

<style>
  template {
    font-size: large;
    background-color: black;
    color: white;
  }


</style>
