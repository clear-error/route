<script setup lang="ts">
import { useRoute, useRouter } from 'vue-router';
const route = useRoute()
const router = useRouter()
</script>

<template>
  <h1>home</h1>
  <div>id: {{ route.params.id }}</div>
  <div>name: {{ route.params.name }}</div>
  <div>age:{{ route.params.age }}</div>
  <button @click="router.back()">prev返回</button>
</template>
test