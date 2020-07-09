<template>
    <div>
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
                <tr v-for="(student, index) in studentList">

                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    data() {
        studentList: [
            { id:1, name: 'Jack', age: 10, gender: 'Male', birthMonth: 7, birthYear: 2008 },
            { id:2, name: 'Jill', age: 10, gender: 'Female', birthMonth: 7, birthYear: 2008 },
            { id:3, name: 'Joe', age: 10, gender: 'Male', birthMonth: 7, birthYear: 2008 },
        ]
    }
}
</script>

<style lang="stylus" scoped>

</style>