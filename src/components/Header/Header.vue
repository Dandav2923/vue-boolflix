<template>
<header class="container-fluid bg-black">
  <div class="row p-3 justify-content-between align-items-center">
    <div class="col-4 img">
      <img src="../../assets/logo.png" alt="">
    </div>
    <SearchFilm
      @doSearch="$emit('searchFilms',($event))"
    />
  </div>
</header>
</template>

<script>
import SearchFilm from "../Header/SearchFilm.vue";
export default {
    name: 'Header',
    components: {
      SearchFilm,
    },
}
</script>

<style>

</style>