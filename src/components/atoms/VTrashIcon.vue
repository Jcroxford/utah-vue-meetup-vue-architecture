<template>
  <div class="delete" @click="$emit('click')"><i class="material-icons">delete</i></div>
</template>

<style scoped>
.delete {
  margin-right: 8px;
}

.material-icons {
  cursor: pointer;
  color: red;
}

.material-icons:hover {
  opacity: 0.7;
}
</style>
