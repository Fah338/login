<template>
  <div>
    <b-container>
      <div>
        <b-card>
          <b-avatar size="250px"></b-avatar><br /><br />
          <b-button variant="primary" @click="login">Login by Google</b-button>
          <b-button variant="danger" @click="logout">LogOut</b-button>
        </b-card>
      </div>
    </b-container>
  </div>
</template>

<script>
import firebase from "firebase/app";
import { auth } from "@/plugin/firebaseConfig.js";
export default {
  data() {
    return {
      email: null,
    };
  },
  methods: {
    login() {
      const provider = new firebase.auth.GoogleAuthProvider();
      console.log("1");

      auth
        .signInWithPopup(provider)
        .then((result) => {
          /** @type {firebase.auth.OAuthCredential} */
          var credential = result.credential;
          this.email = result.email;
          var token = credential.accessToken;
          console.log(token);
          // The signed-in user info.
          var user = result.user;
          console.log(user);
          this.$router.replace("/Admin");
          // ...
        })
        .catch((error) => {
          // Handle Errors here.
          var errorCode = error.code;
          console.log(errorCode);
        });
  
        
     
    },
    logout() {
      auth
        .signOut()
        .then(() => {
          console.log("Sign-out successful");
          alert("Sign Out");
        })
        .catch((error) => {
          console.log(error);
        });
        
    },
  },
};
</script>

<style>
</style>