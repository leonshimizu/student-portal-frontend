<template>
  <div class="verification">
    <form v-on:submit.prevent="submit()">
      <h1>Student Verification</h1>
      <ul>
        <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
      </ul>
      <div>
        <label>Student ID:</label>
        <input type="text" v-model="newSessionParams.student_id" />
      </div>
      <div>
        <label>Email:</label>
        <input type="email" v-model="newSessionParams.email" />
      </div>
      <div>
        <label>Password:</label>
        <input type="password" v-model="newSessionParams.password" />
      </div>
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
  import axios from "axios";
  export default {
    data: function () {
      return {
        newSessionParams: {},
        errors: []
      };
    },
    methods: {
      submit: function () {
        console.log("in the submit function");
        // axios
        //   .post("/sessions", this.newSessionParams)
        //   .then((response) => {
        //     axios.defaults.headers.common["Authorization"] =
        //       "Bearer " + response.data.jwt;
        //     localStorage.setItem("jwt", response.data.jwt);
        //     localStorage.setItem("user_id", response.data.user_id);
        //   })
        //   .catch((error) => {
        //     console.log(error.response);
        //     this.errors = ["Invalid email or password."];
        //     this.email = "";
        //     this.password = "";
        //   });
        this.$router.push("/change_password");
      }
    }
  };
</script>