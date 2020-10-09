<template>
  <form method="post">
    <h1>{{ header }}</h1>
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
    <p>By continuing, you agree to our Condition of Use and Privacy Notice</p>
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

<style scoped>
form {
  display: grid;
  align-items: flex-start;
  justify-items: flex-start;
  padding: 1% 10% 3% 10%;
  width: 100%;
  height: 100%;
}

label,
p {
  font-weight: bold;
}

input {
  border-radius: 4px;
  border-color: rgba(0, 0, 0, 0.6);
  border-style: solid;
  border-width: 1.5px;
  height: 25px;
  width: 100%;
}

input:invalid {
  box-shadow: 0 0 20px 5px red;
}

#Continue {
  font-weight: bold;
  cursor: pointer;
  font-size: 0.9em;
  background-color: var(--orange-Color);
}

#Continue:hover {
  background-color: var(--orange-Color-darker);
}
</style>