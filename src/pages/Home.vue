<template>
  <div>
    <section class="hero">
      <div class="hero-body">
        <p class="title">Find your dream job today</p>
        <p class="subtitle">Apply for any job below</p>
      </div>
    </section>

    <NewJob @save="handelSubmit" />

    <Job v-for="job in jobs" :key="job.id" :job="job" @delete="handelDelete" />
  </div>
</template>

<script>
import Job from "../components/Job.vue";
import NewJob from "../components/NewJob.vue";
import { vacancies } from "../../data";
export default {
  components: { NewJob, Job },
  data() {
    return {
      jobs: vacancies,
    };
  },
  methods: {
    handelSubmit(formData) {
      console.log(formData);
      this.jobs.unshift(formData);
    },
    handelDelete(jobId) {
      this.jobs = this.jobs.filter((job) => job.id !== jobId);
    },
  },
};
</script>

<style></style>
