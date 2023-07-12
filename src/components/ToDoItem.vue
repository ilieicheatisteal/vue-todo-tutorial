// ToDoItem.vue
<template>
  <div v-bind:class="{ 'completed' : todoItem.completed }">
    <p @click="markComplete">{{ todoItem.title }}</p>
    <button @click="$emit('delete-todo-event', todoItem.id)">Löschen</button>
  </div>
</template>

<script>

export default {
  name: 'ToDoItem',
  components: {},
  props: {
    todoItem: {
      type: Object,
      default: () => {}
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
</style>
