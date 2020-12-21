<template>
  <div class="Header" :class="{ menuVisible: isMenuVisible }">
    <nav class="navbar navbar-expand-lg navbar-light Header__navbar">
      <div class="container-fluid">
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
          @click.stop="toggleNavbar()"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <div
          id="navbarNav"
          class="collapse navbar-collapse Header__navbarList d-flex-lg align-items-start"
          :class="{ show: isMenuVisible }"
        >
          <div class="me-auto mb-2 mb-lg-0 Header__title">
            <router-link to="/" class="nav-link">Title</router-link>
          </div>
          <ul class="navbar-nav">
            <li class="nav-item mb-2 mb-lg-0 me-5 Header__link">
              <router-link to="/register" class="nav-link">Link 1</router-link>
            </li>
            <li class="nav-item float-right Header__link">
              <router-link to="/user" class="nav-link">Link 2</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      isMenuVisible: true
    };
  },
  methods: {
    toggleNavbar() {
      this.isMenuVisible = !this.isMenuVisible;
    }
  }
};
</script>

<style lang="sass" scoped>
@import './Header'
</style>
