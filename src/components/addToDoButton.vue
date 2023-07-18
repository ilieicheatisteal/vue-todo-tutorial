//AddToDoButton.vue
<template>
  <div class="background">
  <div>
    <form @submit="addToDo">
      <input type="text" v-model="title" name="title">
      <button type="submit" class="btn btn-primary">Add</button>

    </form>
    <!-- Example split danger button -->
    <div class="btn-group">
      <button type="button" class="btn btn-primary">Filter</button>
      <button type="button" class="btn btn-primary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
        <span class="visually-hidden">Toggle Dropdown</span>
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Completed</a></li>
        <li><a class="dropdown-item" href="#">Not Completed</a></li>
        <li><hr class="dropdown-divider"></li>
        <li><a class="dropdown-item" href="#">No Filter</a></li>
      </ul>
    </div>
  </div>
  </div>
  <div class="background2"></div>
</template>

<script>

import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'AddToDoButton',

  // props: {},
  // emits: {},

  // setup(): Setup {},
  data() {
    return {
      title: ''
    }
  },

  // computed: {},
  // watch: {},

  // beforeCreate() {},
  // created() {},
  // beforeMount() {},
  // mounted() {},
  // beforeUpdate() {},
  // updated() {},
  // activated() {},
  // deactivated() {},
  // beforeUnmount() {},
  // unmounted() {},
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
  // render() {},
}
</script>

<style>
dropdown-menu {
  background-color: cornflowerblue;
}



</style>
