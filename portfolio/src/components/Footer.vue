<template>
  <v-footer
    dark
    padless
    v-if="$route.meta.hideFooter"
  >
    <v-card
      flat
      tile
      class="indigo lighten-1 white--text text-center"
    >
      <v-card-text>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4 white--text"
          icon
          flat
        >
          <v-icon size="24px">
            {{ icon }}
          </v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        If you have a project that you'd like to work on or if you're interested in collaborating, 
        please don't hesitate to reach out to me via my social media accounts. 
        I am always open to new opportunities and partnerships, and I would be happy to discuss your ideas and see how we can work together. I will do my best to get back to you as soon as possible. 
        Thank you for considering me for your project.
      </v-card-text>

      <v-divider class="bg-grey"></v-divider>

      <v-card-text class="white--text text-caption">
        © {{ new Date().getFullYear() }} - All rights Reserved, Developed by Isaac Mhlanga
      </v-card-text>
    </v-card>
  </v-footer>
</template>
  <script>
  export default {
    data: () => ({
      icons: [
        "mdi-facebook",
        "mdi-twitter",
        "mdi-linkedin",
        "mdi-instagram",
        "mdi-github",
      ],
    }),
  };
  </script>
  <style scoped>
  .v-footer {
    background-color: #202236 !important;
    color: white;
  }
  .v-card 
  {
    background-color: #202236 !important;
    color: grey;
  }
  .v-btn {
    color: #fe4b57 !important;
    background-color: transparent !important;
   
  }
  </style>
  