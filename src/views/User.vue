<template>
  <div class="Page">
    <div class="container">
      <header class="Page__header">
        <div class="common-box w-100">
          {{ user.name }} {{user.surname}}'s Page
        </div>
      </header>
      <section>
        <button class="btn btn-success w-25">ACCESS</button>
        <div class="Page__main">
          <div v-if="user.age < 18" class="error-box w-25">
            You should be ate least 18 years old!
          </div>
          <div v-else class="Page__photo">
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: "User",
  data() {
    return {
      user: {}
    }
  },
  mounted() {
    const user = JSON.parse(localStorage.getItem('user'));
    this.user = user;
  }
};
</script>

<style lang="sass">
@import "./Page"
</style>