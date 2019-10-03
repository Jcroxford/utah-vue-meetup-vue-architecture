<template>
  <label class="label" :class="{ strikethrough: strikeThrough }">{{ text }}</label>
</template>

<script>
export default {
  props: {
    text: { type: String, required: true },
    strikeThrough: { type: Boolean, default: false }
  }
}
</script>

<style scoped>
.label {
  margin-left: 5px;
}

.strikethrough {
  text-decoration: line-through;
}
</style>
