<template>
  <form>
    <div class="form-group">
      <label for="name">Name</label>
      <input type="text" id="name" name="name" v-model="studentForm.name">
    </div>
  </form>
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
  .form-group label {
    /* display: block; */
  }
</style>