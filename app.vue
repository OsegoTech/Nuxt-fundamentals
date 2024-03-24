<template>
  <div>
    <NuxtLayout>
      <NuxtPage/>
    </NuxtLayout>
    
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
