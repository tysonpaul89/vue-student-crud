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
      <tr v-for="student in studentArray" :key="student.id">
        <td>{{ student.name }}</td>
        <td>{{ student.age }}</td>
        <td>{{ student.gender }}</td>
        <td class="btn-td"><a id="btn-edit" href="#">Edit</a></td>
        <td class="btn-td"><a id="btn-delete" href="#">Delete</a></td>
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

  td {
    text-align: center;
  }

  #btn-delete,
  #btn-edit {
    color: white;
    text-decoration: none;
    padding: .5em;
  }

  #btn-delete {
    background-color: rgba(255, 0, 0, 0.616);
  }

  #btn-edit {
    background-color: rgba(0, 81, 255, 0.616);
  }
</style>