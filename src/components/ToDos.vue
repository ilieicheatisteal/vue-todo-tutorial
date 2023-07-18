// ToDos.vue
<template>
  <div class="backgroundextension">
  <div>
    <ul>
      <li v-bind:key="`randomg-${item.id}`" v-for="item in todoEntries">
        <ToDoItem v-bind:todoItem="item" @delete-todo-event="deleteToDoItem"/>
      </li>
    </ul>
  </div>
  </div>
</template>

//ToDos.vue
<script>
import ToDoItem from "./ToDoItem";

export default {
  name: 'ToDos',
  components: {
    ToDoItem
  },
  props: {
    todoEntries: {
      type: Array,
    }
  },

  methods: {
   deleteToDoItem(toDoId) {
     this.$emit('delete-todo-event', toDoId);
   }
 },
}
</script>

<style>
.headline {
  color: #186eff;
  font-family: "Arial";
  text-decoration: underline;
  text-decoration-color: #186eff;
  position: center;
}



</style>
