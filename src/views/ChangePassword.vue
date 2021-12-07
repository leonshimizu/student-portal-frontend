<template>
  <div class="change-password">
    <form v-on:submit.prevent="submit()">
      <h1>Change Password</h1>
      <ul>
        <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
      </ul>
      <div>
        <label>Email:</label>
        <input type="email" v-model="editUserParams.email" />
      </div>
      <div>
        <label>Password:</label>
        <input type="password" v-model="editUserParams.password" />
      </div>
      <div>
        <label>Password confirmation:</label>
        <input type="password" v-model="editUserParams.password_confirmation" /><small v-if="editUserParams.password !== editUserParams.password_confirmation" class="text-danger">Passwords must match</small>
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
        editUserParams: {
          email: "",
          password: "",
          password_confirmation: ""
        },
        errors: []
      };
    },
    methods: {
      submit: function () {
        console.log("in the submit function - change password page");
        // axios
        //   .post("/users", this.editUserParams)
        //   .then((response) => {
        //     console.log(response.data);
        //     this.$router.push("/login"); // goes to login page
        //   })
        //   .catch((error) => {
        //     this.errors = error.response.data.errors;
        //   });
      }
    }
  };
</script>