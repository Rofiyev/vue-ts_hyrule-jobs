<template>
  <main>
    <h1>{{ state.title }} - {{ state.age }}</h1>
    <button @click="changeName('Hello Abdulloh!', 20)">click me</button>
  </main>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const state = reactive({
  title: 'Hello Dilshod!' as string,
  age: 18 as number | string
})

function changeName(name: string, age: number | string) {
  state.title = name
  state.age = age
}
</script>

<style scoped></style>
