<template>
    <v-card>
        <v-list-item v-for="movie in movies" :key="movie.imdbID">
            <v-list-item-content>
                <v-list-item-title>{{ movie.Title }}</v-list-item-title>
            </v-list-item-content>
        </v-list-item>
    </v-card>
</template>

<script>
    export default {
        name: "MovieList",
        props:{
            movies:{
                type: Array,
                required: true
            }
        }
    }
</script>

<style scoped>

</style>