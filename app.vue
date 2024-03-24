<template>
  <div>
    <nav>
      <NuxtLink to="/">home</NuxtLink>
      <NuxtLink to="/movies">movies</NuxtLink>
    </nav>
    <NuxtPage/>
  </div>
</template>

<script setup ts>
useHead({
  // title: "My movie Site",
  titleTemplate: (titleChunk) => {
    return titleChunk? `${titleChunk} - My movie site`: "My movie site"
  }
})
</script>
