<template>
  <main class="app">
    <header>
      <div class="title">
        <h1>Hyurle Jobs</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </header>

    <JobListComponent :jobs="jobs" :order="order" />
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import type { IJobs } from '@/interface'
import type { OrderTerm } from '@/types'
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
      ] as IJobs[],
      order: 'title' as OrderTerm
    }
  },
  methods: {
    handleClick(term: OrderTerm) {
      this.order = term
    }
  }
})
</script>

<style scoped>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c5;
  border: 3px solid #1195c5;
  background-color: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
.title h1 {
  font-size: 3em;
  font-family: 'Courgette', handwriting;
}
</style>
