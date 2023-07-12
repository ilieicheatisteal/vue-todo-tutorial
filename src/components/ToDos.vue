// ToDos.vue
<template>
  <div>
    <h1>Meine To-Do-Liste</h1>
    <ul>
      <li v-bind:key="item.id" v-for="item in todoEntries">
        <ToDoItem v-bind:todoItem="item" @delete-todo-event="deleteToDoItem"/>
      </li>
    </ul>

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
 // methods: {
   // deleteToDoItem(toDoId){
 //        ...this.todoEntries.filter(item => item.id !== toDoId)
    //  ];
     // console.log("hallo", toDoId, this.todoEntries.filter(item => item.id !== toDoId));
  //  }
//  },
}
</script>