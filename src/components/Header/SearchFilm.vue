<template>
    <div class="col-4">
        <div class="input-group mb-3">
            <input 
                v-model="inputText"
                name="search"
                type="text" 
                class="form-control" 
                placeholder="Inserisci il titolo del film o della serie che stai cercando" 
                aria-label="Example text with button addon" aria-describedby="button-addon1">
            <button 
                @click="$emit('doSearch', inputText)"
                class="btn btn-outline-secondary p-0 ps-1 pe-1 text-lowercase text-white" 
                type="button" 
                id="button-addon1">Search</button>
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