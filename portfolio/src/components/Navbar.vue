<template>
  <div class="container">
    <v-app-bar
      dense
      app
      class="d-none d-sm-flex and-down"
      v-if="$route.meta.hideNavbar"
    >
      <v-toolbar-title
        class="text-white"><v-icon color="#fe4b57" class="mx-2">mdi-draw</v-icon>Isaac
        Mhlanga</v-toolbar-title
      >
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn
          v-for="item in nav"
          :key="item.icon"
          :to="item.path"
          :title="item.title"
          :prepend-icon="item.icon"
          >{{ item.text }}</v-btn
        >
      </v-toolbar-items>
    </v-app-bar>
    <v-toolbar app class="d-sm-none">
      <v-app-bar-nav-icon @click="dialog = true" color="#fe4b57" size="25">
      </v-app-bar-nav-icon>
      <v-toolbar-title class="text-white">Isaac Mhlanga</v-toolbar-title>

      <v-dialog
        v-model="dialog"
        fullscreen
        hide-overlay
        transition="dialog-left-transition"
      >
        <v-card>
          <v-toolbar>
            <v-toolbar-title class="text-white">Isaac Mhlanga</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon @click="dialog = false">
              <v-icon color="#fe4b57">mdi-close</v-icon>
            </v-btn>
          </v-toolbar>
          <v-divider></v-divider>

          <v-list>
            <v-list-item
              v-for="(item, index) in nav"
              :key="index"
              :to="item.path"
              @click="dialog = false"
            >
             
            <template v-slot:prepend>
              <v-icon :icon="item.icon" color="grey"></v-icon>
            </template>
            <v-list-item-title v-text="item.text"></v-list-item-title>




              <!-- <v-icon
                class="mx-2"
                color="rgb(184, 183, 183)"
                v-if="item.icon"
                >{{ item.icon }}</v-icon
              > -->
             
                <!-- <v-list-item-title class="text-white" :title="item.title">{{
                  item.text
                }}</v-list-item-title> -->
             
            </v-list-item>
          </v-list>
        </v-card>
      </v-dialog>
    </v-toolbar>
  </div>
</template>
<script>
export default {
  data() {
    return {
      dialog: false,
      nav: [
        {
          icon: "mdi-home",
          text: "Home",
          active: true,
          path: "/home",
        },
        {
          icon: "mdi-lightbulb-on",
          text: "Skills",
          active: false,
          path: "/skills",
        },
        {
          icon: "mdi-briefcase",
          text: "Projects",
          active: false,
          path: "/project",
        },
        {
          icon: "mdi-phone",
          text: "Contact",
          title: "Our Contact info",
          active: false,
          path: "/contact",
        },
        {
          icon: "mdi-login",
          text: "Login",
          title: "Login",
          active: false,
          path: "/login",
        },
      ],
    };
  },
};
</script>
<style scoped>
.v-toolbar {
  background-color: #202236 !important;
}
.v-toolbar-items {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  color: grey;
}
.v-toolbar-items .v-btn:hover {
  color: #fe4b57 !important;
  font-size: 14px;
}
.v-list-item-title
{
  color: grey !important;
  padding-left: -1em !important;
}
.v-list {
  background-color: #202236 !important;
  margin-top: -3em;
}
.v-card {
  background: #ccc3c3 !important;
}
</style>
