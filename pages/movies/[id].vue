<script setup>
const route = useRoute()
const {data} = useAsyncData(`/movies/${route.params.id}`,() => {
   return $fetch(`http://www.omdbapi.com/?&apikey=6c94eee8&i=${route.params.id}`)
})


</script>

<template>
    <div>
        <pre>
            {{ data }}
        </pre>
    </div>
</template>