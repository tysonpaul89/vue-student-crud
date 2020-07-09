<template>
  <div class="container">
    <form>
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" id="name" name="name" v-model="studentForm.name" />
      </div>
      <div class="form-group">
        <label for="age">Age</label>
        <input type="text" id="age" name="age" v-model="studentForm.age" />
      </div>
      <div class="form-group">
        <label>Gender</label>
        <input type="radio" name="Male" value="Male" v-model="studentForm.gender">Male
        <input type="radio" name="Female" value="Female" v-model="studentForm.gender">Female
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      studentForm: {
        name: "",
        gender: null,
        birthMonth: null,
        birthYear: null,
        age: 0
      }
    };
  }
};
</script>

<style scoped>
.container {
  width: 60%;
  margin: 0 auto;
  margin-bottom: 10px;
  border: 1px dotted blue;
  padding: 0 10px 10px 10px;
}

.form-group {
  padding-top: 10px;
}

.form-group label {
  padding-right: 10px;
}

.form-group input {
  border-radius: 5px;
  width: 20%;
}
</style>