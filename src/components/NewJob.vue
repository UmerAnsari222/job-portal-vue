<template>
  <div class="box">
    <h1 class="title is-5">Create a job</h1>
    <form @submit.prevent="handelSubmit">
      <input
        v-model="form.title"
        class="input"
        type="text"
        placeholder="Job title"
        required
      />
      <input
        v-model="form.company"
        class="input"
        type="text"
        placeholder="Company"
        required
      />
      <input
        v-model="form.city"
        class="input"
        type="text"
        placeholder="City name"
        required
      />

      <textarea
        v-model="form.description"
        class="input"
        placeholder="Job description"
        required
      ></textarea>
      <button class="button is-primary">Create</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        title: "",
        company: "",
        city: "",
        description: "",
      },
    };
  },
  methods: {
    handelSubmit() {
      this.$emit("save", { ...this.form, id: new Date().getTime().toString() });
      for (let key in this.form) {
        this.form[key] = "";
      }
    },
  },
};
</script>

<style scoped>
input,
textarea {
  margin-bottom: 10px;
}
</style>
