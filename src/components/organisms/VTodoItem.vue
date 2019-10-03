<template>
  <div class="todo-item">
    <VCheckboxGroup
      :value="completed"
      :label="text"
      @input="v => $emit('update:completed', v)"
    />
    <VTrashIcon @click="$emit('delete')" />
  </div>
</template>

<script>
import VCheckboxGroup from '@/components/molecules/VCheckboxGroup'
import VTrashIcon from '@/components/atoms/VTrashIcon'

export default {
  components: { VCheckboxGroup, VTrashIcon },
  props: {
    completed: { type: Boolean, required: true },
    text: { type: String, required: true }
  }
}
</script>

<style scoped>
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

.todo-item:last-child {
  border-bottom: 1px solid #eee;
}
</style>
