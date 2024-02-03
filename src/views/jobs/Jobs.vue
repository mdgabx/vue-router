<template>
  <h2>Jobs</h2>
  <div v-for="job in jobs" :key="job.id">
    <router-link :to="{ name: 'JobDetails', params: { id: job.id }}">
      <h3> {{ job.title }}</h3>
    </router-link>
  </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: [
                { title: 'Web developer', id: 1, details: 'Lorem' },
                { title: 'CyberSecurity', id: 2, details: 'Lorem' },
                { title: 'Data Scientist', id: 3, details: 'Lorem' },
            ]
        }
    }
}
</script>

<style>

</style>