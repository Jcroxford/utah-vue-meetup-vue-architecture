<template>
  <div class="screen-container">
    <div class="content-container">
      <Todo />
    </div>
  </div>
</template>

<script>
import Todo from './components/Todo'

export default {
  name: 'app',
  components: { Todo }
}
</script>

<style>
body {
  margin: 0px;
  font-family: 'Roboto', sans-serif;
}

.screen-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0px;
  width: 100%;
  background-color: #f5f5f5;
}

.content-container {
  background-color: #fff;
  padding: 15px;
  border-radius: 5px;
  min-width: 350px;
  box-shadow: 0px 3px 1px -2px rgba(0, 0, 0, 0.2), 0px 2px 2px 0px rgba(0, 0, 0, 0.14), 0px 1px 5px 0px rgba(0, 0, 0, 0.12)
}
</style>
