<template>
  <div class="container">
    <form>
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" id="name" name="name" v-model="studentForm.name" />
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
  padding: 10px;
}

.form-group label, input {
  margin-right: 10px;
  border-radius: 1em;
}
</style>