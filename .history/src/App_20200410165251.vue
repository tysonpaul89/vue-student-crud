<template>
  <div id="app">
    <StudentListng />
  </div>
</template>

<script>
import StudentListng from './components/StudentListng.vue'

export default {
  name: 'App',
  components: {
    StudentListng
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
