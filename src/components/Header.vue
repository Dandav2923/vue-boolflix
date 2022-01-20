<template>
  <div class="container">
    <SearchFilm
      @doSearch="searchFilms($event)"
    />
  </div>
</template>

<script>
import SearchFilm from "./SearchFilm.vue";
export default {
    name: 'Header',
    components: {
      SearchFilm,
    }
}
</script>

<style>

</style>