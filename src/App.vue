<template>
  <div id="app">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from "@/components/Header/Header.vue";

export default {
  name: "App",
  components: { Header }
}
</script>

<style lang="sass">
$font-family-main: Avenir, Helvetica, Arial, sans-serif
$font-size-main: 16px
$color-font: #2c3e50

*
	box-sizing: border-box

body
  margin: 0

#app
  font-family: $font-family-main
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center

  a
    text-decoration: none
    outline: none
</style>
