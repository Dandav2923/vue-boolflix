<template>
  <div class="container">
      <div class="row">
          <div class="col">
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
      </div>

  </div>
</template>

<script>
export default {
    name: 'Film',
    props: {
        title: String,
        originalTitle: String,
        originalLanguage: String,
        voted: Number,
    }
}
</script>

<style>

</style>