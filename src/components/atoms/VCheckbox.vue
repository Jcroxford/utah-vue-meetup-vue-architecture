<template>
  <input
    :checked="value"
    type="checkbox"
    @click="$emit('input', !value)"
  />
</template>

<script>
export default {
  props: {
    value: { type: Boolean, required: true }
  }
}
</script>
