<script setup>
const route = useRoute()
const {data} = useFetch(`http://www.omdbapi.com/?&apikey=6c94eee8&i=${route.params.id}`, {
    pick: ["Plot", "Title"],
    key: `/movies/${route.params.id}`
})
// const {data} = useAsyncData(`/movies/${route.params.id}`,() => {
//    return $fetch(`http://www.omdbapi.com/?&apikey=6c94eee8&i=${route.params.id}`)
// }, {
//     pick: ["Plot", "Title"]
//     // transform(data){
//     //     return {
//     //         Plot: data.Plot,
//     //         Title: data.Title
//     //     }
//     //      return data.Title
//     // }
// })


</script>

<template>
    <div>
        <pre>
            {{ data }}
        </pre>
    </div>
</template>