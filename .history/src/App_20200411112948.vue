<template>
  <div id="app">
    <StudentForm :type="formType" @studentFormData="addStudent"/>
    <StudentListng :studentArray="students" />
  </div>
</template>

<script>
import StudentListng from './components/StudentListng.vue';
import StudentForm from './components/StudentForm.vue';

export default {
  name: 'App',
  components: {
    StudentListng, // To display student data.
    StudentForm // To Add/Edit student data.
  },
  data() {
    return {
      students: [
        { id:1, name: 'Jack', age: 12, gender: 'Male', birthMonth: 7, birthYear: 2008 },
      ],
      formType: 'create'
    }
  },
  methods: {
    addStudent(data) {
      if (this.formType === 'create') {
        this.students.push(data);
      } else {
        // pass
      }
    }
  }
}
</script>

<style>

</style>
