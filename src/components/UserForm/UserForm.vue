<template>
  <form class="UserForm" @submit.prevent="submitForm">
    <div class="row g-3 align-items-center mb-5">
      <div class="col-auto d-flex">
        <label for="name" class="col-form-label label-box">Name:</label>
      </div>
      <div class="col-auto">
        <input
          v-model="user.name"
          name="name"
          type="text"
          id="userName"
          placeholder="Your name"
          class="form-control"
          aria-label="Your name"
          aria-describedby="userName"
          required
        />
      </div>
      <div class="col-auto d-flex">
        <span v-if="!user.name" id="userName" class="form-text">
          Can contain only letters
        </span>
        <span v-if="user.name && !isTextFieldValid(user.name)" class="error-box">
          Invalid character!
        </span>
      </div>
    </div>

    <div class="row g-3 align-items-center mb-5">
      <div class="col-auto d-flex">
        <label for="surname" class="col-form-label label-box">Surname:</label>
      </div>
      <div class="col-auto">
        <input
          v-model="user.surname"
          name="surname"
          type="text"
          id="userSurname"
          placeholder="Your surname"
          class="form-control"
          aria-label="Your surname"
          aria-describedby="userSurname"
          required
        />
      </div>
      <div class="col-auto d-flex">
        <span v-if="!user.surname" id="userSurname" class="form-text">
          Can contain only letters
        </span>
        <span v-if="user.surname && !isTextFieldValid(user.surname)" class="error-box">
          Invalid character!
        </span>
      </div>
    </div>

    <div class="row g-3 align-items-center mb-5">
      <div class="col-auto d-flex">
        <label for="age" class="col-form-label label-box">Age:</label>
      </div>
      <div class="col-auto">
        <input
          v-model="user.age"
          name="age"
          type="text"
          id="userAge"
          placeholder="Your age"
          class="form-control"
          aria-label="Your age"
          aria-describedby="userAge"
          required
        />
      </div>
      <div class="col-auto d-flex">
        <span v-if="!user.age" id="userAge" class="form-text">
          Can contain only digits
        </span>
        <span v-if="user.age && !isAgeFieldValid(user.age)" class="error-box">
          Invalid character!
        </span>
      </div>
    </div>

    <transition name="UserForm__fade">
      <div v-if="isNameAndSurnameValid" class="common-box w-100 mb-4">
        Hello {{user.name}} {{user.surname}} !
      </div>
    </transition>

    <button
      type="submit"
      class="btn btn-success w-25"
      :disabled="!isFormValid"
    >
      Save
    </button>
  </form>
</template>

<script>
export default {
  name: "UserForm",
  data() {
    return {
      user: {
        name: null,
        surname: null,
        age: null
      },
      state: null
    }
  },
  computed: {
    isFormValid() {
      return Boolean(
        this.user.name &&
        this.user.surname &&
        this.user.age &&
        this.isNameAndSurnameValid &&
        this.isAgeFieldValid(this.user.age)
      )
    },
    isNameAndSurnameValid() {
      const validName = this.isTextFieldValid(this.user.name);
      const validSurname = this.isTextFieldValid(this.user.surname);
      return validName && validSurname;
    }
  },
  methods: {
    submitForm() {
      const dto = this.user;
      console.log('dto', dto)
      this.state = "submitted";
      this.user = {};
      this.$router.push("/user")
    },
    isTextFieldValid(text) {
      var re = /^[A-Za-z]+$/;
      return text && re.test(text);
    },
    isAgeFieldValid(age) {
      return Number(age) && age > 0 && age <= 150;
    }
  }
}
</script>

<style lang="sass" scoped>
@import "./UserForm"
</style>