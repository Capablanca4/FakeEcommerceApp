<template>
  <section class="container">
    <UserAuthForm v-bind:header="'Sign In'" class="UserAuthForm" v-bind:submitForm="logInUser" />
    <nuxt-link to="/Home/register" class="register">
      <button class="register__button">Create a new account</button>
    </nuxt-link>
  </section>
</template>

<script>
import UserAuthForm from "../../components/Home/UserAuthForm";

export default {
  components: {
    UserAuthForm,
  },
  methods: {
    logInUser(logInInfo) {
      this.$auth.loginWith("local", {
        data: logInInfo,
      });
    },
  },
};
</script>

<style lang="scss" scoped>

@import './assets/sass/variables';

.UserAuthForm {
  background-color: $limon-Color-darker;
  width: 60vw;
  height: 70vh;
  margin: 5vh 20vw 5vh 20vw;
}

.register {
  display: inline-block;
  margin-left: 30vw;
  width: 40vw;

  &__button {
    font-weight: bold;
    cursor: pointer;
    border-style: solid;
    background-color: $yellow-Color;
    height: 40px;
    width: 100%;
    font-size: 25px;
    border-radius: 4px;
    border-color: rgba(0, 0, 0, 0.6);
    border-width: 1.5px;
  }
}
</style>