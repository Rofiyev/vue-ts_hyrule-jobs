<template>
  <main>
    <h1>{{ title }} - {{ age }}</h1>
    <button @click="changeName('Hello Abdulloh!', 20)">click me</button>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HomeView',
  components: {},
  data() {
    return {
      title: 'Hello Dilshod!' as string,
      age: 18 as string | number
    }
  },
  methods: {
    changeName(name: string, age: number | string) {
      this.title = name
      this.age = age
      return age
    }
  }
})
</script>

<style scoped></style>
