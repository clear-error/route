<script setup lang="ts">
import { reactive } from 'vue';
import { useRouter } from 'vue-router';
// import data from '../components/data.json';

const data = reactive(
  {
    "first": [{
      id: 1,
      name: 'John Doe',
      age: 25
    },
    {
      id: 2,
      name: 'J',
      age: 30
    },
    {
      id: 3,
      name: 'good',
      age: 35
    }]
  }
)
type Item = {
  id: number;
  name: string;
  age: number;
}
const router = useRouter()
const go = (item: Item) => {
  router.push({
    /*     path: '/home',
        query: params */
    name: 'Home',
    params: {
      id: item.id
    }

  })
}
</script>
<template>
  <div class="about">
    <h1>about</h1>
  </div>
  <table cellspacing="0" border="1">
    <thead>
      <tr>
        <th>id</th>
        <th>name</th>
        <th>age</th>
        <th>operate</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in  data.first">
        <td>{{ item.id }}</td>
        <td>{{ item.name }}</td>
        <td>{{ item.age }}</td>
        <td>
          <button @click="go(item)">go</button>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<style scoped></style>
