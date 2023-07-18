// ToDoItem.vue
<template>
  <div v-bind:class="{ 'completed' : todoItem.completed }">
    <p @click="markComplete">{{ todoItem.title }}</p>
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault" />
      <label class="form-check-label" for="flexCheckDefault"></label>
    </div>
    <button type="button" class="btn btn-outline-danger" data-bs-toggle="tooltip" data-bs-placement="top" data-bs-title="delete todo" @click="$emit('delete-todo-event', todoItem.id)"> <i class="bi bi-trash"></i></button>
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
  // emits: {},

  // setup(): Setup {},
  // data(): Data {
  //   return {};
  // },

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
    markComplete() {
      // eslint-disable-next-line vue/no-mutating-props
      this.todoItem.completed = !this.todoItem.completed;
    }
  },
  // render() {},
}

// eslint-disable-next-line no-unused-vars


</script>

<style>
.completed {

}
 template {
   background-color: black;
 }
</style>
