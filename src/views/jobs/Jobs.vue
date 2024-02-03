<template>
  <h2>Jobs</h2>
  <div v-if="jobs.length">
    <div v-for="job in jobs" :key="job.id">
    <router-link :to="{ name: 'JobDetails', params: { id: job.id }}">
      <h3> {{ job.title }}</h3>
    </router-link>
  </div>
  </div>
  <div v-else>
      Loading...
  </div>
  
</template>

<script>
export default {
    data() {
        return {
            jobs: []
        }
    },
    mounted() {
      this.fetchJobs()
    },
    methods: {
      fetchJobs() {
        fetch('http://localhost:3000/jobs')
        .then((res) => res.json())
        .then((data) => this.jobs = data)
        .catch((err) => console.error(err.message))
      }
    }
}
</script>

<style>

</style>