<template>
  <div>
    <Vh2>Todo List</Vh2>
    <VSearchForm prevent-empty-submit @submit="addTodo" />
    <hr style="opacity: 0;">
    <VTodoItem
      v-for="todo of todos"
      :key="todo.id"
      :completed.sync="todo.completed"
      :text="todo.text"
      @delete="deleteTodo(todo.id)"
    />
  </div>
</template>

<script>
import Vh2 from '@/components/atoms/Vh2'
import VSearchForm from '@/components/molecules/VSearchForm'
import VTodoItem from '@/components/organisms/VTodoItem'

const createId = () => Math.floor(Math.random() * 10000)

export default {
  components: { VSearchForm, Vh2, VTodoItem },
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
    addTodo (text) {
      this.todos.push({ id: createId(), completed: false, text })
    }
  }
}
</script>
