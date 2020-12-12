<template>
  <div class="Header">
    <router-link to="/" class="Header__title">Title</router-link>
    <router-link to="/register" class="Header__link">Link 1</router-link>
    <router-link to="/user" class="Header__link">Link 2</router-link>
  </div>
</template>

<script>
  export default {
    name: "Header"
  }
</script>

<style lang="sass" scoped>
@import './Header'
</style>