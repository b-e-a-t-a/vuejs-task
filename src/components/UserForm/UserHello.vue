<template>
  <div class="common-box w-100 mb-4">
    Hello {{ user.name }} {{ user.surname }} !
  </div>
</template>

<script>
export default {
  name: "UserHello",
  props: {
    user: Object
  }
}
</script>

<style lang="sass" scoped>
@import "./UserForm"
</style>
