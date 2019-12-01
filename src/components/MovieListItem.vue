<template>
    <v-card width="300">
        <v-img width="300" height="450" :src="imageURL"/>
        <v-card-title>{{movie.Title}}</v-card-title>
        <v-card-subtitle class="mx-auto">{{movie.Year}}</v-card-subtitle>
    </v-card>
</template>

<script>
    import unknownImage from '@/assets/unknown.jpg'
    export default {
        name: "MovieListItem",
        props:{
            movie:{
                type: Object,
                required: true
            }
        },
        computed:{
            imageURL(){
                return this.movie.Poster === 'N/A' ? unknownImage : this.movie.Poster
            }
        }
    }
</script>

<style scoped>

</style>