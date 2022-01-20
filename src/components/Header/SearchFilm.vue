<template>
  <div class="container">
      <div class="row p-3">
          <div class="col-4">
              <div class="input-group mb-3">
                <button 
                    @click="$emit('doSearch', inputText)"
                    class="btn btn-outline-secondary" 
                    type="button" 
                    id="button-addon1">Search</button>
                <input 
                    v-model="inputText"
                    name="search"
                    type="text" 
                    class="form-control" 
                    placeholder="Inserisci il titolo del film" 
                    aria-label="Example text with button addon" aria-describedby="button-addon1">
            </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'SearchFilm',
    props: {
        value: {
            type: String,
        }
    },
    data() {
        return {
            inputText:'',
        }
    }
}
</script>

<style>

</style>