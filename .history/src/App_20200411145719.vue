<template>
  <div id="app">
    <StudentForm
      :type="formType"
      :studentData="student"
      @studentFormData="addStudent"
      @resetForm="onFromReset"/>
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
  watch: {
    students() {
      return [{ id:1, name: 'Jack', age: 12, gender: 'Male', birthMonth: 7, birthYear: 2008 },];
    }
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
    addStudent(studentData) {
      if (this.formType === 'create') {
        this.students.push(studentData);
      } else {
       const index = this.students.findIndex(stud => stud.id == studentData.id);
       this.students[index] = studentData;
      }
    },
    onStudentEdit(studentId) {
      this.formType = 'edit';
      this.student = this.students.find(student => student.id === studentId)
    },
    onStudentDelete(studentId) {
      this.students = this.students.filter(student => student.id !== studentId)
    },
    onFromReset() {
      this.formType = 'create';
      this.student = null;
    }
  }
}
</script>

<style>

</style>
