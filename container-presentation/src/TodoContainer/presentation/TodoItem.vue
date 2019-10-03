<template>
  <div class="todo-item">
    <div>
      <input
        :checked="completed"
        type="checkbox"
        @click="$emit('update:completed', !completed)"
      >
      <label class="checkbox-label" :class="{ complete: completed }">{{ text }}</label>
    </div>
    <div class="delete" @click="$emit('delete')"><i class="material-icons">delete</i></div>
  </div>
</template>

<script>
export default {
  props: {
    completed: { type: Boolean, required: true },
    text: { type: String, required: true }
  }
}
</script>

<style scoped>
.checkbox-label {
  margin-left: 5px;
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
