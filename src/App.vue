<template>
    <v-app>
        <v-app-bar
                app
                color="primary"
                dark
        >
            <div class="d-flex align-center">
                <h1>Searching Movie</h1>
            </div>
        </v-app-bar>

        <v-content>
            <Search @search="changeMovieResults"/>
            <MovieList :movies="movies"/>
        </v-content>
    </v-app>
</template>

<script>
    import Search from "@/components/Search";
    import MovieList from "@/components/MovieList";

    export default {
        name: 'App',

        components: {
            MovieList,
            Search,
        },


        data() {
            return {
                movies: []
            }
        },
        methods: {
            changeMovieResults(results) {
                this.movies = results
            }
        }

    };
</script>
