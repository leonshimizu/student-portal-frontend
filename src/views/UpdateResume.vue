<template>
  <div class="Resume">
    <h1>{{ message }}</h1>

    <p>first_name: <input type="text" v-model="editUserParams.first_name"></p>
    <p>first_name: <input type="text" v-model="editUserParams.first_name"></p>
    <p>email: <input type="text" v-model="editUserParams.email"></p>
    <p>phone_number: <input type="text" v-model="editUserParams.phone_number"></p>
    <p>bio: <input type="text" v-model="editUserParams.bio"></p>
    <p>linkedin_url: <input type="text" v-model="editUserParams.linkedin_url"></p>
    <p>twitter_handle: <input type="text" v-model="editUserParams.twitter_handle"></p>
    <p>website_url: <input type="text" v-model="editUserParams.website_url"></p>
    <p>resume_url: <input type="text" v-model="editUserParams.resume_url"></p>
    <p>github_url: <input type="text" v-model="editUserParams.github_url"></p>
    <p>photo: <input type="text" v-model="editUserParams.photo"></p>
    <button v-on:click="updateFunction()">Update</button>

  </div>
</template>

<style></style>

<script>
import axios from "axios";
  export default {
    data: function () {
      return {
        message: "Update Your Resume!",
        editUserParams: {}
      };
    },
    created: function () {},
    methods: {
      updateFunction: function() {
        console.log("in the update function");
        axios 
          .patch(``, this.editUserParams)
          .then(response => {
            console.log(response.data);
          })
      }
    },
  };
</script>