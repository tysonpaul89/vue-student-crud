<template>
  <div id="app">
    <StudentForm @studentFormData="addStudent"/>
    <StudentListng :studentArray="students" />
  </div>
</template>

<script>
import StudentListng from './components/StudentListng.vue';
import StudentForm from './components/StudentForm.vue';

export default {
  name: 'App',
  components: {
    StudentListng,
    StudentForm
  },
  data() {
    return {
      students: [
        { id:1, name: 'Jack', age: 12, gender: 'Male', birthMonth: 7, birthYear: 2008 },
        { id:2, name: 'Jill', age: 12, gender: 'Female', birthMonth: 7, birthYear: 2008 },
        { id:3, name: 'Joe', age: 12, gender: 'Male', birthMonth: 7, birthYear: 2008 },
      ]
    }
  },
  methods: {
    addStudent(data) {
      console.log(data);
      this.students.push(data);
    }
  }
}
</script>

<style>

</style>
