// * eslint-disable *
<template>
    <section>
        <div class="row">
            <div class="col-6">
                <h1>film</h1>
                 <div class="cover">
                    <img 
                        :src="'https://image.tmdb.org/t/p' + img">
                </div>
                <div class="title">
                    {{ title }}
                </div>
                <div class="original-title">
                    {{ originalTitle }}
                </div>
                <div class="original-language">
                    <i :class="'flag flag-' + getFlags(originalLanguage)" ></i>
                </div>
                <div class="voted">
                    {{ voted }}
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Film',
    props: {
        title: String,
        originalTitle: String,
        originalLanguage: String,
        voted: Number,
        getFlags: Function,
        img: Image,
        src: String
    },
}
</script>

<style>

</style>