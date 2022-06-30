<template>
  <div class="box">
    <h1 class="title is-5">{{ job.title }}</h1>
    <span>{{ job.company }}</span>
    <p>{{ job.city }}</p>
    <div class="block"></div>
    <p>
      {{ job.description }}
    </p>
    <div class="is-flex is-justify-content-space-between">
      <button @click="handelApply(job)" class="button is-primary mt-4">
        Apply
      </button>
      <button @click="handelClick(job)" class="button is-danger mt-4">
        Delete
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    job: Object,
  },
  methods: {
    handelClick(job) {
      this.$emit("delete", job.id);
    },
    handelApply(job) {
      alert(`Applyed succesfully for ${job.title}`);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>