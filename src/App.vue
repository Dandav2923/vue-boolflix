// * eslint-disable *
<template>
<div id="app">
    <Header @searchFilms="searchFilms($event)"/>
    <Main  
        :films="films"
        :series="series"
    />
</div>
</template>

<script>
import Header from "./components/Header/Header.vue";
import Main from "./components/Main/Main.vue";
import axios from 'axios';

export default {
name: "App",
components: {
    Header,
    Main,
},
data() {
    return {
        inputTextSearch:'',
        films: null,
        series: null,
        query: 'https://api.themoviedb.org/3/search/movie',
        querySeries: 'https://api.themoviedb.org/3/search/tv'
    }
},
methods: {
    searchFilms(value) {
        this.inputTextSearch = value
        console.log(this.inputTextSearch);
        this.callAxiosFilm();
    },
    callAxiosFilm () {
        axios.get(
            this.query, {
                params: {
                    api_key: 'df5b914f4cb568985555883d8eeec9a2',
                    query: this.inputTextSearch
                }
            }
        )
        .then((results) => {
            this.films = results.data.results;
            console.log(this.films);
            });
        axios.get(
            this.querySeries, {
                params: {
                    api_key: 'df5b914f4cb568985555883d8eeec9a2',
                    query: this.inputTextSearch
                }
            })
            .then((results) => {
                this.series = results.data.results;
                console.log(this.series);
            })
        }
    },
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
@import '~mdb-ui-kit/css/mdb.min.css';

</style>
