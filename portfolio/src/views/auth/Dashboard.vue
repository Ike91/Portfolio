<template>
  <div>
    <NavDash />
   
   
    
  </div>
</template>
<script>
import NavDash from "../../components/NavDash.vue";
import Skills from "../../components/Skills.vue";


export default {
  components: {
    NavDash,
    Skills,
  },
  data() {
    return {
      dialog: false,
      isLoading: false,
      name: "",
      role: "",
      phone: "",
      email: "",
      about: "",
      projects: [],

      icons: [
        "mdi-facebook",
        "mdi-twitter",
        "mdi-linkedin",
        "mdi-instagram",
        "mdi-github",
      ],
    };
  },

  mounted() {
    
  },

  methods: {
  
  },
};
</script>
<style scoped>
.v-card
{
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  background: rgb(219, 210, 210);
  height: 200px;
}
</style>
