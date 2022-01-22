// * eslint-disable *
<template>
    <section>
        <div class="row">
            <div class="col-6 card">
                <h1>tv series</h1>
                <div v-if="img == null">
                    {{ alt }}
                </div>
                <div 
                    v-else 
                    class="cover">
                    <img 
                        :src="src + img">                       
                </div>
                <div class="title">
                    {{ name }}
                </div>
                <div class="original-title">
                    {{ originalName }}
                </div>
                <div class="original-language">
                    <i :class="'flag flag-' + getFlags(originalLanguage)"></i>
                </div>
                <div
                    class="voted">
                    <span>
                        <i 
                        v-for="number in 5"
                        :key="number"
                        :class="(number <= getStar(voted)) ? 'fas fa-star': 'far fa-star'"></i>
                    </span>
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

    },
}
</script>

<style>

</style>