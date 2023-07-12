// ToDoItem.vue
<template>
  <div v-bind:class="{ 'completed' : todoItem.completed }">
    <p @click="markComplete">{{ todoItem.title }}</p>
    <button type="button" class="btn btn-danger" @click="$emit('delete-todo-event', todoItem.id)"> <i class="fa-solid fa-trash"></i>Delete</button>
  </div>
</template>


<script>

export default {
  name: 'ToDoItem',
  components: {},
  props: {
    todoItem: {
      type: Object,
    }
},
  methods: {
    markComplete() {
      // eslint-disable-next-line vue/no-mutating-props
      this.todoItem.completed = !this.todoItem.completed;
    }
  }
}

</script>

<style>
.completed {
  text-decoration: line-through;
}
 template {
   background-color: black;
 }
</style>
