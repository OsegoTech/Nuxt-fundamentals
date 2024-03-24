<script setup>
const route = useRoute()
const { data, error } = await useFetch(`http://www.omdbapi.com/?&apikey=6c94eee8&i=${route.params.id}`, {
    pick: ["Plot", "Title", "Error"],
    key: `/movies/${route.params.id}`,
    // onResponse({request, response}){
    //     if(response._data.Error === "Incorrect IMDb ID."){
    //         showError({statusCode: 404, statusMessage: "Page Not Found"})
    //     }
    // },
    // onResponseError (){
    //     showError({statusCode: 500, statusMessage: "Ooh noes!"})
    // }
})
if (error.value){
    // handle accordingly
}
if (data.value.Error === "Incorrect IMDb ID.") {
    showError({ statusCode: 404, statusMessage: "Page Not Found" })
}
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