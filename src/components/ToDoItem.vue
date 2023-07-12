// ToDoItem.vue
<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" integrity="sha512-iecdLmaskl7CVkqkXNQ/ZH/XLlvWZOJyj7Yy7tcenmpD1ypASozpmT/E0iPtmFIB46ZmdtAc9eNBvH0H/ZpiBw==" crossorigin="anonymous" referrerpolicy="no-referrer" />
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
