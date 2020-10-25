<template>
  <div>
    <UserAuthForm
      v-bind:header="'Register'"
      v-bind:hasName="true"
      class="UserAuthForm"
      v-bind:submitForm="registerUser"
    />
  </div>
</template>

<script>
import UserAuthForm from "../../components/Home/UserAuthForm";

export default {
  components: {
    UserAuthForm,
  },
  methods: {
    registerUser(logInInfo) {
      /* eslint no-console: "error" */
      console.log(logInInfo);
    },
  },
};
</script>

<style lang="scss" scoped>

@import './assets/sass/variables';

.UserAuthForm {
  background-color: color(darker-limon);
  width: 60vw;
  height: 70vh;
  margin: 5vh 20vw 5vh 20vw;
}
</style>