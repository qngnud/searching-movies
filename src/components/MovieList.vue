<template>
    <v-container fluid>
        <v-flex class="d-flex flex-wrap flex-row">
            <v-flex class="pb-5" v-for="movie in movies" :key="movie.imdbID">
                <MovieListItem :movie="movie"/>
            </v-flex>
            <v-spacer>

            </v-spacer>
        </v-flex>
    </v-container>

</template>

<script>
    import MovieListItem from "@/components/MovieListItem";

    export default {
        name: "MovieList",
        props: {
            movies: {
                type: Array,
                required: true
            }
        },
        components: {
            MovieListItem
        }
    }
</script>

<style scoped>

</style>