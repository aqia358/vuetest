<template>
  <div id="todo-list-example">
    <input
      v-model="newTodoText"
      v-on:keyup.enter="addNewTodo"
      placeholder="Add a todo"
    >
    <ul>
      <todoItem
        v-for="(todo, index) in todos"
        v-bind:key="todo.id"
        v-bind:title="todo.title"
        v-on:remove="todos.splice(index, 1)"
      ></todoItem>
    </ul>
  </div>
</template>


<script>
  import TodoItem from './TodoItem.vue'

  export default {
    components: {TodoItem},
    data () {
      return {
        newTodoText: '',
        todos: [
          {
            id: 1,
            title: 'Do the dishes'
          },
          {
            id: 2,
            title: 'Take out the trash'
          },
          {
            id: 3,
            title: 'Mow the lawn'
          }
        ],
        nextTodoId: 4
      }
    },
    methods: {
      addNewTodo () {
        this.todos.push({
          id: this.nextTodoId++,
          title: this.newTodoText
        })
        this.newTodoText = ''
      }
    }
  }
</script>
