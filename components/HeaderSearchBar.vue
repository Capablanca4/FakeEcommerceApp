<template>
  <div class="searchBar">
    <select class="searchBar__select" v-model="reserchCriteria">
      <option
        v-for="crit in criteria"
        :key="crit"
        v-bind:value="crit"
      >{{ crit[0].toUpperCase().concat(crit.substring(1))}}</option>
    </select>
    <input type="text" class="searchBar__input" v-model="reserchText" />
    <nuxt-link class="searchBar__validate" v-bind:to="routeToStore">
      <font-awesome-icon :icon="['fas', 'search']" class="searchBar__magnifier" />
    </nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      criteria: ["all", "categories", "product"],
      reserchCriteria: "all",
      reserchText: "",
    };
  },
  computed: {
    routeToStore: function () {
      if (this.reserchText !== "") {
        return `/Store/${this.reserchCriteria}/${this.reserchText}`;
      }
      return "/Store";
    },
  },
};
</script>

<style scoped>
.searchBar {
  display: flex;
  border-radius: 5px;
  width: 900px;
  height: 100%;
}

.searchBar > * {
  height: 75%;
  margin-top: 8.75px;
}

.searchBar__select {
  display: block;
  cursor: pointer;
  font-weight: 700;
  font-size: 0.8em;
  padding: 0.6em 1.1em 0.5em 0.2em;
  width: 12%;
  max-width: 12%;
  border: 1px solid #aaa;
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
  -moz-appearance: none;
  -webkit-appearance: none;
  appearance: none;
  background-color: #fff;
  background-image: url("data:image/svg+xml;charset=US-ASCII,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22292.4%22%20height%3D%22292.4%22%3E%3Cpath%20fill%3D%22%23007CB2%22%20d%3D%22M287%2069.4a17.6%2017.6%200%200%200-13-5.4H18.4c-5%200-9.3%201.8-12.9%205.4A17.6%2017.6%200%200%200%200%2082.2c0%205%201.8%209.3%205.4%2012.9l128%20127.9c3.6%203.6%207.8%205.4%2012.8%205.4s9.2-1.8%2012.8-5.4L287%2095c3.5-3.5%205.4-7.8%205.4-12.8%200-5-1.9-9.2-5.5-12.8z%22%2F%3E%3C%2Fsvg%3E"),
    linear-gradient(to bottom, #dddddd 0%, #afacac 100%);
  background-repeat: no-repeat, repeat;
  background-position: right 0.3em top 50%, 0 0;
  background-size: 0.65em auto, 100%;
}
.searchBar__select::-ms-expand {
  display: none;
}
.searchBar__select:hover {
  border-color: #888;
}

.searchBar__select option {
  font-weight: normal;
}

.searchBar__input {
  width: 80%;
}

.searchBar__validate {
  cursor: pointer;
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
  width: 9%;
  background-color: var(--orange-Color);
}

.searchBar__magnifier {
  height: 100%;
  width: 100%;
  padding: 15%;
}
</style>