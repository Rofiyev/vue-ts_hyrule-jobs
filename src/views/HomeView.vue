<template>
  <main>
    <JobListComponent :jobs="jobs" />
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import type { IJobs } from '../interface'
import JobListComponent from '@/components/JobListComponent.vue'

export default defineComponent({
  name: 'HomeView',
  components: { JobListComponent },
  data() {
    return {
      jobs: [
        { id: '1', title: 'farm worker', location: 'lon lon ranch', salary: 30_000 },
        { id: '2', title: 'quarryman', location: 'death mountain', salary: 40_000 },
        { id: '3', title: 'then lost words', location: 'flute player', salary: 25_000 },
        { id: '4', title: 'fisherman', location: 'lake hylia', salary: 21_000 },
        { id: '5', title: 'prison guard', location: 'gerudo valley', salary: 32_000 }
      ] as IJobs[]
    }
  }
})
</script>

<style scoped></style>
