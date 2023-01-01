<template>
    <v-container>
      <div class="login-section">
        <div class="errorAlert">
          <v-snackbar v-model="showError" color="error" timeout="4000" v-if="ErrorMessage" vertical="top" app>
            {{ ErrorMessage }}
          </v-snackbar>
        </div>
        <div class="login-header">
          <h1>Login</h1>
        </div>
      </div>

    
      <div class="login-section">
        <v-row justify="center">
          <v-col md="4" >
            <v-card class="login-card" elevation="1">
              <v-responsive class="pt-4 text-center">
                <v-avatar size="100px" class="bg-grey lighten-2">
                  <img src="./ike.png" alt="avator" />
                </v-avatar>
                <p class="text-grey mt-2">Isaac Mhlanga</p>
              </v-responsive>
  
              <v-card-text>
                <v-form @submit.prevent>
                  <v-text-field
                    v-model="email"
                    name="email"
                    label="Email"
                    type="text"
                 
                    required
                    :rules="emailRules"
                    prepend-icon="mdi-account"
                  ></v-text-field>
  
                  <v-text-field
                    v-model="password"
                    name="password"
                    label="Password"
                   
                    required
                    outlined
                    :rules="passwordRules"
                    :type="show ? 'password' : password"
                    @click:append-inner="show = !show"
                   :append-inner-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
                    prepend-icon="mdi-lock"
                  ></v-text-field>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn to="resetPassword" class="text-caption"> Forgot password? </v-btn>
                    <v-btn  @click="login()" class="text-caption">  Sign in</v-btn>
                  </v-card-actions>
                </v-form>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </div>
    </v-container>
  </template>
  <script>
  import { mapState } from 'vuex';
  export default {
    data() {
      return {
       
        showError: true,
        register: true,
        show: true,
        valid: false,
        email: "",
        password: "",
  
        emailRules: [
          (v) => !!v || "Email is required",
          (v) => /.+@.+/.test(v) || "Email must be valid",
        ],
  
        passwordRules: [
          (v) => !!v || "Password is required",
          (v) => v.length >= 6 || "Password must be 6 charecters long",
        ],
      };
    },
   computed: {
    ...mapState({
      ErrorMessage: state => state.ErrorMessage,
  }),
   },
    methods: {

      dismissError() {
        this.ErrorMessage = null;
      },

      login: function () {
        
        const valid = true
        if (valid) 
        {
          this.$store.dispatch("sigin", {
            email: this.email,
            password: this.password,
          });
        }
      },
      created() {
        if(this.ErrorMessage) {
          setTimeout(() => {
            this.dismissError();
          }, 3000);
        }
      },
    },
  };
  </script>
  <style scoped>
  .login-section {
    padding-top: 20px;
  }
 
  .v-container {
    margin-bottom: 5em;
  }
  
  .login-header {
    text-align: center;
    color: rgb(77, 76, 76);
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    padding: 1rem;
    position: relative;
  }
  
 
  .login-card {
    background: rgb(219, 210, 210) !important;
    padding-right: 15px;
    border-radius: 8px;
    
  }
  .v-conatiner {
    margin: 10em !important;
  }
  .v-btn {
    background-color: #fe4b57 !important;
    color: white !important;
   
   
  }
  .v-btn:hover {
    background-color: #c0bcbc !important;
    color: #fe4b57;
  }
  @media only screen and (max-width: 600px) {
    .v-container {
      padding-bottom: 1em !important;
      border-radius: 10px !important;
      margin-top: -4em !important;
      
    }
    .login-section {
     margin-top: -1.5rem;
    }
  }
  
  </style>
  