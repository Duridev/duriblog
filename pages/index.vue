<script setup>
const { data } = await useAsyncData('posts', () => queryContent().find())
</script>

<template>
  <div>
    <h1>Entradas del blog 📝</h1>
    <ul>
      <li v-for="post in data" :key="post._path">
        <NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
      </li>
    </ul>
  </div>
</template>
