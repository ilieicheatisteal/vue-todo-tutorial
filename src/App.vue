// App.vue
<template>
  <div id="app">
    <ToDos v-bind:todoEntries="todoEntries" @delete-todo-event="deleteTodDoItem" />
    <AddToDoButton @add-todo-event="addToDoItem" />
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
          title: 'Infos sammeln',
          completed: false
        },
        {
          id: 2,
          title: 'Test Projekt erstellen',
          completed: false
        },
        {
          id: 3,
          title: 'Blog Beitrag schreiben',
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
