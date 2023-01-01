<template>
    <div class="container">
      <v-snackbar color="error" v-model="showError" timeout="4000" v-if="ErrorMessage">
        {{ ErrorMessage }}
      </v-snackbar>
      <v-snackbar color="success" timeout="4000" v-if="SuccessMessage">
        {{ SuccessMessage }}
      </v-snackbar>
      <div>
        <p class="text-center">Enter the email you are registered with below</p>
      </div>
      <v-card>
        <v-card-text>
          <form ref="form" @submit.prevent="resetPassword">
            <v-text-field 
            :rules="emailRules"
            label="Email" 
            type="email" 
            prepend-icon="mdi-email" 
            v-model="email">
    
            </v-text-field>
            <v-card-actions>
              <v-btn class="text-caption mx-8" :loader="isReseting" @click="resetPassword" >Submit</v-btn>
            </v-card-actions>
          </form>
        </v-card-text>
        
      </v-card>
      
    </div>
  </template>
  
<script>
import { mapState } from 'vuex';
export default {
  data() {
    return {

      isReseting: false,
      email: '',

      emailRules: [
        (v) => !!v || "Email is required",
        (v) => /.+@.+/.test(v) || "Email must be valid",
      ],
    };
  },
  methods: {

    //reset form
    resetForm() {
      this.$refs.form.reset();
    },

    resetPassword: function(){
    
    //clear the form
    this.resetForm()

    //start the laoder
    this.isReseting = true;

    this.$store.dispatch("resetPassword", {
        email: this.email,
    })

    //stop the loader
    this.isReseting = false;
   }
  },
  computed: {
    ...mapState({
      ErrorMessage: state => state.ErrorMessage,
      SuccessMessage: state => state.SuccessMessage,
  }),
   },
};
</script>
<style scoped>
.resetPassword-header {
  text-align: center;
  color: rgb(77, 76, 76);
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  padding: 1rem;
  position: relative;
}

.v-btn {
  background-color: #ccc3c3 !important;
  color: grey;
  width: 100px;
}
.v-card {
  background: rgb(219, 210, 210) !important;
  padding-right: 15px;
  padding-top: 15px;
  border-radius: 8px;
  margin-top: 2rem;
  margin-bottom: 4rem;
  
}
</style>