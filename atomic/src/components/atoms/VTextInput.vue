<template>
  <input
    :value="value"
    type="text"
    :placeholder="placeholder"
    @input="$emit('input', $event.target.value)"
  />
</template>

<script>
export default {
  props: {
    value: { type: String, required: true },
    placeholder: { type: String, default: 'Type here' }
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
</style>
