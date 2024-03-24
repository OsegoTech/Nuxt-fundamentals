<script setup>
const route = useRoute()
const {data} = useAsyncData(() => {
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