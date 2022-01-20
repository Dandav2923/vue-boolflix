<template>
    <main class="container">
            <Film
                v-for="(element, index) in films"
                :key=" 'Id' + index"
                :title="element.title"
                :original-title="element.original_title"
                :original-language="element.original_language"
                :voted="element.vote_average"
            />
            <Series
                v-for="(element, index) in series"
                :key=" 'IdS' + index"
                :name="element.name"
                :originalName="element.original_name"
                :originalLanguage="element.original_language"
                :voted="element.vote_average"
            />
    </main>
</template>

<script>
// import SearchFilm from "./SearchFilm.vue";
import Film from "./Film.vue";
import Series from "./Series.vue";
// import axios from 'axios';

export default {
    name: 'Main',
    props: [
        'films' ,
        'series' 
    ],
    components: {
        Film,
        Series,
        // SearchFilm,
    },
    // data() {
    //     return {
    //         inputTextSearch:'',
    //         film: null,
    //         query: 'https://api.themoviedb.org/3/search/movie',
            
    //     }
    // },
    // methods: {
    //     searchFilms(value) {
    //         this.inputTextSearch = value
    //         console.log(this.inputTextSearch);
    //         this.callAxios()
    //     },
    //     callAxios () {
    //         axios.get(this.query, {
    //             params: {
    //                 api_key: 'df5b914f4cb568985555883d8eeec9a2',
    //                 query: this.inputTextSearch
    //             }
    //         })
    //         .then((results) => {
    //             this.film = results.data.results;
    //         })
    //     }
    // },
}
</script>

<style>

</style>