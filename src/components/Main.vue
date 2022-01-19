<template>
  <div class="container">
      <div class="row">
          <Film />
      </div>
  </div>
</template>

<script>
import axios from 'axios';
import Film from "./Film.vue";
export default {
    name: 'Main',
    components: {
        Film,
    },
    data (){
        return {
            queryApi: 'https://api.themoviedb.org/3/search/movie?api_key=df5b914f4cb568985555883d8eeec9a2'
        }
        },
        methods: {
            getQueryApi(){
                axios.get(`${this.queryApi}`)
                .then()
                .catch()
            }
        }
}
</script>

<style>

</style>