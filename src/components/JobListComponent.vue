<template>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>{{ job.salary }} rupeas</p>
        </div>
        <div class="description">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil expedita aliquid
            explicabo commodi cumque ducimus labore saepe! In mollitia obcaecati quo recusandae
            perspiciatis soluta voluptatibus repellat, sunt, quisquam, delectus nulla.
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import type { PropType } from 'vue'
import type { IJobs } from '@/interface'
import type { OrderTerm } from '@/types'

export default defineComponent({
  name: 'JobListComponent',
  props: {
    jobs: {
      required: true,
      type: Array as PropType<IJobs[]>
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>
    }
  }
})
</script>

<style scoped>
.job-list {
  max-width: 960px;
  margin: 40px auto;
}
.job-list ul {
  padding: 0;
}
.job-list li {
  list-style-type: none;
  background: white;
  padding: 16px;
  margin: 16px 0;
  border-radius: 4px;
}
.job-list h2 {
  margin: 0 0 10px;
  text-transform: capitalize;
}
.salary {
  display: flex;
}
.salary img {
  width: 30px;
}
.salary p {
  color: #17bf66;
  font-weight: bold;
  margin: 10px 4px;
}
</style>
