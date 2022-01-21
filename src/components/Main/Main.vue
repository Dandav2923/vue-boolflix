// * eslint-disable *
<template>
    <main class="container">
            <Film
                v-for="(element, index) in films"
                :key=" 'Id' + index"
                :title="element.title"
                :original-title="element.original_title"
                :original-language="element.original_language"
                :voted="element.vote_average"
                :getFlags="getFlagsMethods"
                :src="'https://image.tmdb.org/t/p/w300'"
                :img="element.poster_path"
                :alt="element.title"
                :getStar="getStar"
            />
            <Series
                v-for="(element, index) in series"
                :key=" 'IdS' + index"
                :name="element.name"
                :originalName="element.original_name"
                :originalLanguage="element.original_language"
                :voted="element.vote_average"
                :getFlags="getFlagsMethods"
                :src="'https://image.tmdb.org/t/p/w300'"
                :img="element.poster_path"
                :alt="element.name"
                :getStar="getStar"
            />
    </main>
</template>

<script>
import Film from "./Film.vue";
import Series from "./Series.vue";
export default {
    name: 'Main',
    props: [
        'films' ,
        'series' 
    ],
    components: {
        Film,
        Series,
    },
    methods: {
        getFlagsMethods(value){
            if(value == 'en') {
                return 'us'
            } 
            else {
                return value
            }
        },
        getStar(value){
            return Math.floor(value / 2);
        },
        
    },
}
</script>

<style>

</style>