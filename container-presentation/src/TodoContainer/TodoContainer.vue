<template>
  <div>
    <TodoSearch
      v-model="todoText"
      @create-todo="addTodo"
    />
    <hr style="opacity: 0;">
    <TodoItem
      v-for="todo of todos"
      :key="todo.id"
      :completed.sync="todo.completed"
      :text="todo.text"
      @delete="deleteTodo(todo.id)"
    />
  </div>
</template>

<script>
import TodoSearch from '@/components/presentation/TodoSearch'
import TodoItem from '@/components/presentation/TodoItem'

const createId = () => Math.floor(Math.random() * 10000)

export default {
  components: { TodoSearch, TodoItem },
  data () {
    return {
      todoText: '',
      todos: [
        { id: createId(), completed: false, text: 'first todo' },
        { id: createId(), completed: true, text: 'second todo' }
      ]
    }
  },
  methods: {
    deleteTodo (id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo () {
      if (!this.todoText) return

      this.todos.push({ id: createId(), completed: false, text: this.todoText })
      this.todoText = ''
    }
  }
}
</script>
