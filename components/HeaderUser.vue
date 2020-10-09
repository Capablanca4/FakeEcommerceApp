<template>
  <div v-if="$auth.loggedIn" class="user" v-on:click="logOut">
    <font-awesome-icon :icon="['far', 'user-circle']" class="user__icon" />
    <p class="user__text">Hello, {{ $auth.user.email }}</p>
  </div>
  <nuxt-link v-else class="user" to="/Home/logIn">
    <font-awesome-icon :icon="['far', 'user-circle']" class="user__icon" />
    <p class="user__text">Login</p>
  </nuxt-link>
</template>

<script>
export default {
  methods: {
    logOut: function() {}
  }
};
</script>

<style scoped>
.user {
  color: white;
  height: 75%;
  margin-top: 8.75px;
}

.user__icon {
  display: flex;
  align-items: center;
  height: 60%;
  width: 100%;
}

.user__text {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
