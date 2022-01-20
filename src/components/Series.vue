<template>
    <section>
        <div class="row">
            <div class="col-6">
                <h1>tv series</h1>
                <div class="title">
                    {{ name }}
                </div>
                <div class="original-title">
                    {{ originalName }}
                </div>
                <div class="original-language">
                    {{ originalLanguage }}
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
    name: 'Series',
    props: {
        name: String,
        originalName: String,
        originalLanguage: String,
        voted: Number,
    }
}
</script>

<style>

</style>