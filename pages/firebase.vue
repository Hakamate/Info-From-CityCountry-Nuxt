<template>
  <div>
    <Nav />
    <div>
      <button @click="getRealData">Test</button>
      {{this.getData}}
    </div>
  </div>
</template>

<script>
import Nav from "~/components/Nav.vue";
import firebase from "firebase";
import functions from 'firebase-functions';
require("firebase/auth");

export default {
  components: {
    Nav
  },
  data() {
    return {
      getData: []
    };
  },
  mounted: async function() {
    this.getData = await this.getDataFirebase();
    // https://www.youtube.com/watch?v=ifOzAyR1cG4
    // https://www.youtube.com/watch?v=CK2XEyVGc6c
  },
  methods: {
    getDataFirebase: async function() {
      // await firebase.auth().createUserWithEmailAndPassword(
      //   "foo5555@foo.foo",
      //   "te888888st"
      // );
      return new Promise(resolve => {
        firebase
          .database()
          .ref()
          .on("value", function(snapshot) {
            resolve(snapshot.val().users);
          });
      });
    },
    getRealData: async function() {
      this.getData = await this.getDataFirebase();
    }
  }
};
</script>

