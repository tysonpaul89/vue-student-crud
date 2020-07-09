<template>
    <div class="container">
        <table>
            <thead>
                <tr>
                    <th>Sl.No.</th>
                    <th>Name</th>
                    <th>Age</th>
                    <th>Gender</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(student, index) in studentList" :key="student.id">
                    <td>{{ index }}</td>
                    <td>{{ student.name }}</td>
                    <td>{{ student.age }}</td>
                    <td>{{ student.gender }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
}
</script>

<style scoped>
    table {
        border-collapse: collapse;
        width: 60%;
        margin: 0 auto;
    }

    table, td, th{
        border: 1px solid black;
    }
</style>