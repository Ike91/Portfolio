<template>
    <div>
      <NavDash />
      <div class="container">
        <v-row class="work-experience" elvation="9"> 
            <v-col cols="12" md="6" lg="4" xl="3">
                  <img src="/profile-pic (1).png" alt="Card image" />
            </v-col>
            <v-col class="about-content ml-15" cols="12" md="12" lg="6" xl="6">
              <div class="text-center name-header pt-3">
                <h1>Isaac Ike Mhlanga</h1>
                <h5>Software developer</h5>
            <div class="pt-1">
              <span style="color: #fe4b57">
                <v-icon class="mx-0">mdi-phone</v-icon>
                +27 671004050
              </span>
              <span style="color: #fe4b57">
                <v-icon class="mx-1">mdi-email</v-icon>
               isaac.mhlanga13@gmail.com
              </span>
             
            </div>
            </div>
             <p class="pt-2 text-center">Lorem ipsum dolor sit amet consectetur, adipisicing elit. 
                Suscipit ut consequatur dignissimos rem maiores repellat placeat ex reiciendis quia,
                accusamus soluta quo autem quisquam repudiandae voluptates tempora. Qui quas eum et illum,
                pariatur fugit aliquid nostrum minima distinctio! Eius necessitatibus, iure, nostrum voluptatem
                voluptatum dolores unde architecto, cupiditate culpa ab corrupti neque dicta. Blanditiis sequi 
             </p>
                <div class="text-center icon-color pb-3">
                  <a  v-for="icon in icons" :key="icon.icon" :href="icon.link" target="_blank">
                  <v-btn
                  color="grey"
                  class="mx-2 btn-radius"
                  :icon="icon.icon"
                  size="small"
                ></v-btn>
                  </a>
                  <br>
                  <v-btn class="mt-3" to="wwww.resume" target="_blank" style="border-radius: 20px"> resume </v-btn>
                </div>
               
            </v-col>
          </v-row>
      </div>
     

    </div>
</template>
<script>
import NavDash from "../../components/NavDash.vue";
import About from "../../components/About.vue";
export default{
    components: {
        NavDash,
        About
    },

    data(){
        return{
            icons: [
        {
          icon: "mdi-facebook",
          link: "https://www.facebook.com/profile.php?id=100072606405818",
        },
        {
          icon: "mdi-twitter",
          link: "https://twitter.com/_Isaac_ike1",
        },
        {
          icon: "mdi-linkedin",
          link: "https://www.linkedin.com/in/isaac-mhlanga-31ba62217",
        },
        {
          icon: "mdi-instagram",
          link: "https://www.instagram.com/_isac_i",
        },
        {
          icon: "mdi-github",
          link: "https://github.com/Ike91",
        }
      ],

        }
    }
}
</script>
<style scoped>
.work-experience
{
  margin-top: 7rem;
  background-color: #2d3047;
  color: white;
  border-top-left-radius: 50%;
  border-bottom-left-radius: 50%;
  border-bottom-right-radius: 50%;
  border-top-right-radius: 50%;
  border: 1px solid #2d3047;
  box-shadow: 11px 9px 17px 5px #202236;
 -webkit-box-shadow: 11px 9px 17px 5px #888ba5;
-moz-box-shadow: 11px 9px 17px 5px #202236;
margin-bottom: 8rem;
}
img {
    width: 100%;
    height: auto;
   opacity: .9;
    margin-top: 2.5rem;
    
  }
  .v-btn {
    background: #ff4a57 !important;
    color: white !important;
    
   
   
  }
  .v-btn:hover
  {
    background: transparent !important;
  }
  .icon-color a 
  {
    text-decoration: none !important;
  }
  @media only screen and (max-width: 1200px) {
    .work-experience
    {
      border: none !important;
      box-shadow: none !important;
      margin-top: -1.5rem;
    }
    .about-content
    {
      margin-left: 0 !important;
      
    }
  
  
  }
</style>