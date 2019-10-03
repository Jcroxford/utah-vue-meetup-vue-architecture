<template>
  <div>
    <h2>Todo List</h2>
    <div>
      <form @submit.prevent="addTodo">
        <input v-model="todoText" type="text" placeholder="What needs to be done?">
      </form>
    </div>
    <hr style="opacity: 0;">
    <div v-for="todo of todos" :key="todo.text" class="todo-item">
      <div>
        <input type="checkbox" v-model="todo.completed">
        <label class="checkbox-label" :class="{ complete: todo.completed }">{{ todo.text }}</label>
      </div>
      <div class="delete" @click="deleteTodo(todo.id)"><i class="material-icons">delete</i></div>
    </div>
  </div>
</template>

<script>
const createId = () => Math.floor(Math.random() * 10000)
export default {
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

<style scoped>
input[type='text'] {
  width: 100%;
  border: none;
  border-bottom: 1px solid #ccc;
  font-size: 18px;
  outline: none;
}
.checkbox-label {
  margin-left: 5px;
}

h2 {
  font-weight: 400;
}

.todo-item {
  border: 1px solid #eee;
  width: 100%;
  border-bottom: none;
  padding-left: 8px;
  padding-top: 13px;
  padding-bottom: 13px;
  display: flex;
  justify-content: space-between;
}
.todo-item .delete {
  margin-right: 8px;
}
.complete {
  text-decoration: line-through;
}

.todo-item:last-child {
  border-bottom: 1px solid #eee;
}
.material-icons {
  cursor: pointer;
  color: red;
}
.material-icons:hover {
  opacity: 0.7;
}
</style>
