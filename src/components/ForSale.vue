<template>
  <div class="container mt-5 pt-5">
    <div class="row">
      <div class="col text-center">
        <h5>Our Agents</h5>
      </div>
    </div>
    <div class="d-flex justify-content-around">
      <div
        v-for="(user, index) in users"
        :key="user.key"
        @click="ShowAgent = index"
      >
        <div v-if="ShowAgent === -1 || ShowAgent === index">
          <div class="col text-center pb-5">
            <p>{{ user.name.first }} {{ user.name.last }}</p>
            <img v-bind:src="user.picture.large" />
          </div>
        </div>
      </div>
      <div
        v-if="ShowAgent >= 0"
        class="container bg-dark text-light d-flex align-items-center"
      >
      <p class="badge badge-secondary">Back</p>
        <p class="lead">
          Hey there i'm {{ users[ShowAgent].name.first }}
          {{ users[ShowAgent].name.last }}. I've been involved in the
          {{ users[ShowAgent].location.city }} area for 15 years and counting.
          It would be my honor to serve as your Real Estate agent, whether thats
          selling or buying.
        </p>
        
        <ul class="list-group list-group-flush">
          <li class="list-group-item bg-dark">
            Phone: {{ users[ShowAgent].phone }}
          </li>

          <li class="list-group-item bg-dark">
            Email: {{ users[ShowAgent].email }}
          </li>
          <li class="list-group-item bg-dark">
            Region: {{ users[ShowAgent].location.city }},
            {{ users[ShowAgent].location.state }}
          </li>
          
        </ul>
        
      </div>
    </div>
  </div>
</template>

<script>
const axios = require("axios").default;

export default {
  data() {
    return {
      users: null,
      ShowAgent: -1,
    };
  },
  mounted() {
    axios
      .get("https://randomuser.me/api/?results=5&nat=us")
      .then((response) => (this.users = response.data.results));
  },
};
</script>

<style scoped></style>
