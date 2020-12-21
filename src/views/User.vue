<template>
  <div class="Page">
    <div class="container">
      <header class="Page__header">
        <div  class="common-box w-100">
          <span v-if="userInfoAvailable">{{ user.name }} {{ user.surname }}'s Page</span>
          <span v-else>No user info</span>
        </div>
      </header>
      <section>
        <button class="btn btn-success w-25" :disabled="!userInfoAvailable" @click="showInfo">
          ACCESS
        </button>
        <div v-if="isInfoShown" class="Page__main">
          <div v-if="Number(user.age) < 18" class="error-box w-25">
            You should be at least 18 years old!
          </div>
          <div v-else class="Page__photo">
            <img src="https://source.unsplash.com/p2ifKHu3dXM" alt="welcome picture" />
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
      user: {},
      isInfoShown: false
    };
  },
  mounted() {
    const user = JSON.parse(sessionStorage.getItem("user"));
    this.user = user;
  },
  computed: {
    userInfoAvailable() {
      return Boolean(this.user && this.user.name && this.user.surname)
    }
  },
  methods: {
    showInfo() {
      this.isInfoShown = true;
    }
  }
};
</script>

<style lang="sass">
@import "./Page"
</style>
