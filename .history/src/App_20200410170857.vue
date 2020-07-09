<template>
  <div id="app">
    <StudentListng :studentArray="students" />
  </div>
</template>

<script>
import StudentListng from './components/StudentListng.vue';

export default {
  name: 'App',
  components: {
    StudentListng
  },
  data() {
    return {
      students: [
        { id:1, name: 'Jack', age: 10, gender: 'Male', birthMonth: 7, birthYear: 2008 },
        { id:2, name: 'Jill', age: 10, gender: 'Female', birthMonth: 7, birthYear: 2008 },
        { id:3, name: 'Joe', age: 10, gender: 'Male', birthMonth: 7, birthYear: 2008 },
      ]
    }
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
