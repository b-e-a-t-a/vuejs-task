<template>
  <transition name="Loader__fade">
    <clip-loader
      class="Loader"
      :color="color"
      :size="size"
    />
  </transition>
</template>

<script>
import ClipLoader from "vue-spinner/src/ClipLoader.vue";

export default {
  name: "Loader",
  components: {
    ClipLoader
  },
  data() {
    return {
      color: "#fff",
      size: "23px"
    }
  }
}
</script>

<style lang="sass">
@import './Loader'
</style>