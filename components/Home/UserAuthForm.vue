<template>
  <form method="post" class="form">
    <h1 class="form__header">{{ header }}</h1>
    <label for="name" v-if="hasName">Name</label>
    <input type="text" id="name" v-if="hasName" v-model="logInInfo.name" required />
    <label for="email">Email</label>
    <input
      type="email"
      id="email"
      v-model="logInInfo.email"
      required
      pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,4}$"
    />
    <label for="password">Password</label>
    <input type="password" id="password" v-model="logInInfo.password" required minlength="8" />
    <input type="submit" id="Continue" value="Continue" @click="submitForm(logInInfo)" />
    <p class="form__small">By continuing, you agree to our Condition of Use and Privacy Notice</p>
  </form>
</template>

<script>
export default {
  props: {
    header: {
      type: String,
      default: "",
    },
    hasName: {
      type: Boolean,
      default: false,
    },
    submitForm: {
      type: Function,
      default: null,
    },
  },
  data() {
    return {
      logInInfo: {
        name: null,
        email: "",
        password: "",
      },
    };
  },
};
</script>

<style lang="scss" scoped>

@import './assets/sass/variables';

.form {
  display: flex;
  flex-direction: column;
  align-items: self-start;
  justify-content: space-around;
  padding: 1% 10% 3% 10%;
  font-size: 30px;

  &__header{
    align-self: center;
    margin: 0 auto;
    font-size: 1.2em;
  }

  & label,
  p {
    font-weight: bold;
  }

  & input {
    border-style: solid;
    border-color: rgba(0, 0, 0, 0.6);
    border-width: 1.5px;
    border-radius: 4px;
    font-size: 20px;
    height: 40px;
    width: 100%;
  
    &:invalid {
      box-shadow: 0 0 20px 5px red;
    }
  }

  &__small{
    font-size: initial;
  }
}


#Continue {
  font-weight: bold;
  cursor: pointer;
  font-size: 0.9em;
  background-color: color("orange");

  &:hover {
    background-color: color(darker-orange);
  }
}
</style>