//AddToDoButton.vue
<template>
  <div class="background">
  <div>
    <form @submit="addToDo">
      <input type="text" v-model="title" name="title">
      <button type="submit" class="btn btn-primary"><i class="fa-solid fa-plus"></i>Add</button>
    </form>
  </div>
  </div>
  <div class="background2"></div>
</template>

<script>

import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'AddToDoButton',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addToDo(event){
      event.preventDefault();

      const newToDoObject = {
        id: uuidv4(),
        title: this.title,
        completed: false
      }

      this.$emit("add-todo-event", newToDoObject);
      this.title= '';
    }
  }
}
</script>

<style>
.background {
  height: 100%;
  width: 100%;
  background-color: green;
}
</style>
