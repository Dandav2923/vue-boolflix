<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <Header @searchFilms="searchFilms($event)"/>
    <Main  :films="films" />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from 'axios';

export default {
  name: "App",
  components: {
    // HelloWorld,
    Header,
    Main,
  },
  data() {
        return {
            inputTextSearch:'',
            films: [],
            query: 'https://api.themoviedb.org/3/search/movie',
            
        }
    },
    methods: {
        searchFilms(value) {
            this.inputTextSearch = value
            console.log(this.inputTextSearch);
            this.callAxios()
        },
        callAxios () {
            axios.get(this.query, {
                params: {
                    api_key: 'df5b914f4cb568985555883d8eeec9a2',
                    query: this.inputTextSearch
                }
            })
            .then((results) => {
                this.films = results.data.results;
            })
        }
    },
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
@import '~mdb-ui-kit/css/mdb.min.css';

</style>
