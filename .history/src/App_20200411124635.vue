<template>
  <div id="app">
    <StudentForm :type="formType" :studentData="student" @studentFormData="addStudent"/>
    <StudentListng
      @editStudent="onStudentEdit"
      @deleteStudent="onStudentDelete"
      :studentArray="students" />
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
      formType: 'create',
      student: null,
    }
  },
  methods: {
    addStudent(data) {
      if (this.formType === 'create') {
        this.students.push(data);
      } else {
        // TODO: Edit student
      }
      this.student = null;
    },
    onStudentEdit(studentID) {
      console.log(studentID);
      // this.student = this.students.find
    },
    onStudentDelete(studentID) {
      this.students = this.students.filter(student => student.id !== studentID)
    }
  }
}
</script>

<style>

</style>
