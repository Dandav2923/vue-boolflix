<template>
    <section>
        <div class="row">
            <div class="col-6">
                <div class="title">
                    {{ title }}
                </div>
                <div class="original-title">
                    {{ originalTitle }}
                </div>
                <div class="original-language">
                    {{ originalLanguage }}
                </div>
                <div class="voted">
                    {{ voted }}
                </div>
            </div>
            <div class="col-6">
                <div class="series">
                    {{ name }}
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
        name: String,
    }
}
</script>

<style>

</style>