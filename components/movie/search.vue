<script  setup>



const query = ref("sex education")
const movies = ref([])
async function search (){
    const {Search} = await $fetch(`http://www.omdbapi.com/?i=tt3896198&apikey=6c94eee8&s=${query.value}`)
    movies.value = Search
}

search()
</script>

<template>
  <form @submit.prevent="search">
    <input type="text" v-model="query">
    <button >Search</button>
  </form>
  <ul style="display: flex; flex-wrap: wrap; gap: 10px; list-style: none;">
    <li v-for="movie in movies" :key="movie.imdbID">
        <NuxtLink :to="{name: 'movies-id', params:{id: movie.imdbID}}">
            <img :src="movie.Poster" :alt="movie.Title"
        </NuxtLink>
    </li>
  </ul>
</template>

<style scoped></style>
