// App.vue
<template>
  <div class="app">
    <div class="headline1">
      <h1 class="headline"><i class="bi bi-check-square-fill"></i>My Todo-s</h1></div>
    <AddToDoButton @add-todo-event="addToDoItem"/>
    <ToDos v-bind:todoEntries="todoEntries" @delete-todo-event="deleteTodDoItem"/>

  </div>
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
          title: 'Buy groceries for next week',
          completed: false
        },
        {
          id: 2,
          title: 'Renew car insurance',
          completed: false
        },
        {
          id: 3,
          title: 'Sign up for online course',
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


.app {
  width: 500px;
  height: 100%;
  background-color: lightgrey;
  position: relative;
  top: 30px;
  left: 35%;
  border-radius: 4px;
  padding: 5px;
  border: solid grey 2px;
}


</style>
