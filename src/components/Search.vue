<template>
    <v-container>
        <v-flex>
            <v-text-field v-model="searchQuery" @keyup.enter="search" outlined placeholder="Enter the movie's name">

            </v-text-field>
            <span v-if="error">{{error}}</span>
        </v-flex>
    </v-container>
</template>

<script>
    const BASE_URL = `https://www.omdbapi.com/?apikey=${process.env.VUE_APP_OMDB_KEY}`
    import axios from 'axios'

    export default {
        name: "Search",
        data() {
            return {
                searchQuery: '',
                url: BASE_URL,
                error: ''
            }
        },
        methods: {
            async search () {
                let response = await axios.get(`${BASE_URL}&s=${this.searchQuery}`)
                if (response.status === 200) {
                    let data = response.data
                    if (data.Response === 'True') {
                        this.error = ''
                        return this.$emit('search', data.Search)
                    } else  this.error = data.Error
                }
            }
        }
    }
</script>

<style scoped>

</style>