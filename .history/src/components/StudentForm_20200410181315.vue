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
      <div class="form-group">
        <label for="month">Birth Month</label>
        <select name="month" id="month" v-model="studentForm.birthMonth">
          <option value=""></option>
        </select>
      </div>
      <div class="form-group">
        <label for="year">Birth Year</label>
        <select name="year" id="year" v-model="studentForm.birthYear">
          <option value=""></option>
        </select>
      </div>
      <button type="button">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  computed: {
    year: () => {
      const yearLimit = new Date().getFullYear() - 5;
      const year = [2000];
      for(let i=2000; i < yearLimit; i++) {
        year.push(i);
      }
    }
  },
  data() {
    return {
      studentForm: {
        name: "",
        gender: null,
        birthMonth: null,
        birthYear: null,
        age: 0
      },
      month: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
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

.form-group input[type="text"] {
  border-radius: 5px;
  width: 20%;
}
</style>