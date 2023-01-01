<template>
  <v-container fluid>
    <div class="container">
      <div class="about">
        <v-responsive
          class="pt-4 text-center about"
          v-for="isaac in about"
          :key="isaac.name"
        >
          <v-responsive>
            <v-avatar size="400px" class="bg-grey lighten-2 avatar">
              <img src="/ike.jpeg" alt="avator" />
            </v-avatar>
          </v-responsive>
          <h1>{{ isaac.name }}</h1>
          <h3 style="color: grey" class="mb-2">{{ isaac.role }}</h3>
          <span style="color: #fe4b57">
            <v-icon class="mx-0">mdi-phone</v-icon>
            {{ isaac.phone }}
          </span>
          <span style="color: #fe4b57">
            <v-icon class="mx-1">mdi-email</v-icon>
            {{ isaac.email }}
          </span>
          <div class="summary">
            <p>
              {{ isaac.about }}
            </p>
          </div>
          <v-btn
            v-for="icon in icons"
            :key="icon"
            color="grey"
            class="mx-2 btn-radius"
            :icon="icon"
            size="small"
          ></v-btn>
          <br />
          <v-btn class="resumeBtn"> resume </v-btn>
        </v-responsive>
      </div>
    </div>
  </v-container>
</template>
<script>
import { firestore } from "../Firebase/firebase";
export default {
  data() {
    return {
      icons: [
        "mdi-facebook",
        "mdi-twitter",
        "mdi-linkedin",
        "mdi-instagram",
        "mdi-github",
      ],
      show: false,
      about: [],
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      firestore
        .collection("profile")
        .get()
        .then((querySnapshot) => {
          querySnapshot.forEach((doc) => {
            this.about.push(doc.data());
          });
        });
    },
  },
};
</script>
<style scoped>
.summary
{
  margin-top: 7px;
}
.about h1 {
  color: #fe4b57;

  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
}
.about h3 {
  color: white;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  margin-bottom: 3px;
}
.about p {
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  font-size: 16px;
 
}

.v-btn {
  color: #fe4b57 !important;
  background: transparent !important;
  border: 1px solid #fe4b57;
}
.resumeBtn {
  margin-top: 2em;
  border-radius: 20px;
  color: white;
  font-size: 14px !important;
}
.text-white {
  margin-bottom: 5px !important;
}
.education {
  padding-bottom: 2em !important;
  margin-top: 1em;
}
.education-section {
  margin-bottom: 3em;
}
.education-section p {
  color: grey;
}
.education-section h6 {
  color: white;
}
.v-avatar {
  border: 2px solid #fe4b57 !important;
}
.v-icon {
  color: #fe4b57;
}

@media only screen and (max-width: 600px) {
  .v-container {
    margin-top: -5em !important;
    padding: 0;
  }
}
@media screen and (max-width: 600px) {
  .summary {
    width: 100%;
    margin-left: 0;
    margin-top: 3px;
  }
}
@media screen and (max-width: 320px) {
  .avatar {
    width: 200px !important;
    height: 200px !important;
  }

  .avatar img {
    width: 200px !important;
    height: 200px !important;
  }
}
</style>
