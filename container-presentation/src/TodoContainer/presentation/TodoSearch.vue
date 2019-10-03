<template>
  <div>
    <h2>Todo List</h2>
    <div>
      <form @submit.prevent="$emit('create-todo')">
        <input
          :value="value"
          type="text"
          placeholder="What needs to be done?"
          @input="$emit('input', $event.target.value)"
        >
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    value: { type: String, required: true }
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
h2 {
  font-weight: 400;
}
</style>
