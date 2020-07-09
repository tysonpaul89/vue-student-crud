<template>
  <table>
    <thead>
      <tr>
        <th>Sl.No.</th>
        <th>Name</th>
        <th>Age</th>
        <th>Gender</th>
        <th colspan="2">Action</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(student, index) in studentArray" :key="student.id">
        <td>{{ index }}</td>
        <td>{{ student.name }}</td>
        <td>{{ student.age }}</td>
        <td>{{ student.gender }}</td>
        <td><button id="btn-edit">Edit</button></td>
        <td><button id="btn-delete">Delete</button></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    studentArray: Array
  }
};
</script>

<style scoped>
table {
  border-collapse: collapse;
  width: 60%;
  margin: 0 auto;
}

table,
td,
th {
  border: 1px solid black;
}
</style>