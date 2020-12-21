<template>
  <div class="Page">
    <div class="container">
      <header class="Page__header">
        <div class="common-box">
          User Data
        </div>
      </header>
      <UserForm />
    </div>
  </div>
</template>

<script>
import UserForm from "@/components/UserForm/UserForm.vue";

export default {
  name: "Register",
  components: { UserForm }
};
</script>

<style lang="sass">
@import "./Page"
</style>
