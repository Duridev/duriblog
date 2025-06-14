<script setup>
const { data: posts } = await useAsyncData('posts', () => queryContent().find())
</script>

<template>
  <div class="max-w-3xl mx-auto p-8">
    <h1 class="text-4xl font-bold text-center mb-6 text-indigo-700">🧘‍♂️ Bienvenido a mi blog personal</h1>
    <p class="text-center text-gray-600 mb-12">Pensamientos, reflexiones, y algo de código</p>

    <div>
      <h2 class="text-2xl font-semibold text-gray-800 mb-4">Entradas recientes</h2>
      <ul class="space-y-3">
        <li v-for="post in posts" :key="post._path" class="p-4 bg-white rounded-xl shadow hover:bg-indigo-50 transition">
          <NuxtLink :to="post._path" class="text-lg font-medium text-indigo-700 hover:underline">
            {{ post.title }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>
