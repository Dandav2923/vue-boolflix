// * eslint-disable *
<template>
    <section>
        <div class="row">
            <div class="col">
                <div class="card bg-dark text-white m-2">
                    <div v-if="img == null" >
                        <img class="img-not-found" src="https://cdn.download.it/ms/static/images/poster-placeholder.png" alt="">
                    </div>
                    <div v-else class="--bs-bg-opacity: 1">
                        <img 
                        :src="src + img"
                        class="card-img img-film" alt="...">
                    </div>
                        <div class="card-img-overlay overflow-auto">
                            <h2 class="card-title">{{ name }}</h2>
                            <p class="card-text">Titolo Originale : {{ originalName }}</p>
                            <p class="card-text">Paese di origine :
                            <i :class="'flag flag-' + getFlags(originalLanguage)"></i>
                            <span class="d-block">Voto medio
                            <i 
                                v-for="number in 5"
                                :key="number"
                                :class="(number <= getStar(voted)) ? 'fas fa-star': 'far fa-star'"></i>
                            </span>
                            </p>
                            <p>
                                Trama : {{overview}}
                            </p>
                        </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    name: 'Series',
    props: {
        name: String,
        originalName: String,
        originalLanguage: String,
        voted: Number,
        getFlags: Function,
        img: String,
        src: String,
        alt: String,
        getStar: Function,
        overview: String,

    },
}
</script>

<style lang="scss" scoped>
.img-not-found {
    width: 342px;
}
.card-img-overlay {
    display: none;
}
.card {
    &:hover .card-img-overlay {
        display: block;
        background-color: rgba($color: #000000, $alpha: 0.8) !important;
    }
}

</style>