<template>
  <div class="container">
    <form>
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" id="name" name="name" v-model="studentForm.name" />
      </div>
      <div class="form-group">
        <label>Gender</label>
        <input type="radio" name="Male" value="Male" v-model="studentForm.gender">Male
        <input type="radio" name="Female" value="Female" v-model="studentForm.gender">Female
      </div>
      <div class="form-group">
        <label for="month">Birth Month</label>
        <select name="month" id="month" v-model="studentForm.birthMonth">
          <option v-for="(month, index) in months" :key="index" :value="index">{{month}}</option>
        </select>
      </div>
      <div class="form-group">
        <label for="year">Birth Year</label>
        <select name="year" id="year" v-model="studentForm.birthYear">
          <option v-for="(year, index) in years" :key="index" :value="year">{{year}}</option>
        </select>
      </div>
      <button type="button" @click="onSubmit()">{{ type === 'create' ? 'Add' : 'Edit' }}</button>
      <button type="button" @click="onReset()">Reset</button>
    </form>
  </div>
</template>

<script>
export default {
  props: ['type', 'studentData'],
  computed: {
    years: () => {
      const yearLimit = new Date().getFullYear() - 5;
      const years = [];
      for(let i=2000; i < yearLimit; i++) {
        years.push(i);
      }
      return years;
    }
  },
  data() {
    return {
      studentForm: {
        id: 0,
        name: "",
        gender: null,
        birthMonth: null,
        birthYear: null,
      },
      months: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    };
  },
  beforeUpdate() {
    // console.log(this.type, this.studentData);
    if(this.type === 'edit' && this.studentData) {
      this.studentForm = this.studentData
    }
  },
  methods: {
    onSubmit() {
      const today = new Date()
      let student = {};
      if (this.type === 'create') {
        student.id = today.getMilliseconds();
      } else {
        student.id = this.studentForm.id;
      }

      student.name = this.studentForm.name;
      student.age =  today.getFullYear() - this.studentForm.birthYear;
      student.gender = this.studentForm.gender;
      student.birthMonth = this.studentForm.birthMonth;
      student.birthYear = this.studentForm.birthYear;
      // Pass to the parent element.
      this.$emit('studentFormData', student)
    },
    onReset() {
      this.studentForm = {
        id: 0,
        name: "",
        gender: null,
        birthMonth: null,
        birthYear: null,
      }
      this.$emit('resetForm')
    }
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

button {
  margin-top: 10px;
  margin-right: 5px;
}
</style>