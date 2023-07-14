// ToDos.vue
<template>
  <div class="backgroundextension">
  <div>
    <h1 class="headline">My To-Do-List <i class="fa-solid fa-list"></i></h1>
    <h3 class="marker"><p></p><i class="fa-solid fa-circle-info"></i>Click on task to cross it out</h3>
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
  color: red;
  font-family: "Comic Sans MS";
  background-color: black;
}

.marker {
  background-color: yellow;
  width: 80%;
}

backgroundextension {
  height: 100%;
  width: 100%;
  background-color: green;
}
</style>
