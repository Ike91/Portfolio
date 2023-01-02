<template>
  <div class="container">
    <About/>
    <v-cantainer>
      <v-row class="work-experience"> 
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
            </div>
        </v-col>
      </v-row>
    </v-cantainer>
    <v-container class="skill-container" app>
      <div class="skill-header">
        <span><h3><v-icon style="color: #ff4a57 !important;">mdi-lightbulb-on</v-icon> <span class="skills-adjust"></span></h3></span>
      </div>
        <hr style="color: #6c6c69 !important" />
      <div class="skills">
        <p>
          I am skilled in a variety of technologies, including programming
          languages such as c#, Java, and C++, as well as web development
          frameworks such as vue and laravel, and database management systems
          such as MySQL. I have experience working with these skills in a
          variety of personal projects, and have a strong understanding of how
          to apply them to solve complex problems and develop innovative
          solutions.
        </p>
          <v-btn class="text-caption" to="/skills">Go to skills</v-btn>
      </div>
      <v-row class=" pt-3"> 
        <v-col cols="12" md="6" lg="4" xl="4">
          <v-card elevation="9">
            <v-card-text>
              <p>Experience working with HTML5</p>
              <p>Experience working with CSS3</p>
              <p>Experience working with Javascript</p>
              
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="6" lg="4" xl="4">
          <v-card elevation="9">
            <V-card-text>
              <p>Experience working with java</p>
              <p>Experience working with c++</p>
              <p>Experience working with c#</p>
             
            </V-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="6" lg="4" xl="4">
          <v-card elevation="9">
            <v-card-text>
              <p>Experience working with laravel</p>
              <p>Experience working with Vue.js</p>
              <p>Experience working with PHP</p>
             
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="6" lg="4" xl="4">
          <v-card elevation="9">
            <v-card-text>
              <p>Experience working with laravel</p>
              <p>Experience working with Vue.js</p>
              <p>Experience working with PHP</p>
             
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="6" lg="4" xl="4">
          <v-card elevation="9">
            <v-card-text>
              <p>Experience working with laravel</p>
              <p>Experience working with Vue.js</p>
              <p>Experience working with PHP</p>
            
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="6" lg="4" xl="4">
          <v-card elevation="9">
            <v-card-text>
              <p>Experience working with laravel</p>
              <p>Experience working with Vue.js</p>
              <p>Experience working with PHP</p>
              
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <v-container>
      <div class="skill-header">
        <h3><v-icon style="color: #ff4a57 !important;">mdi-briefcase</v-icon></h3>
      </div>

      <hr style="color: #888ba5 !important" />
      <div>
        <p>
          I have gained a strong foundation in various technologies through
          building personal projects and tutoring computer science students at
          different universities. Some of the projects I have worked on include
          this web application using vue.js framework and firebase as my
          database, I have also tutored students in topics such as data
          structures, algorithms, and software engineering, helping them to
          understand complex concepts. Through these experiences, I have gained
          a deep understanding of a wide range of technologies and have
          developed the skills and knowledge necessary to apply them
          effectively.
        </p>
        <v-btn class="text-caption" to="/project">Go to projects</v-btn>
      </div>
    </v-container>
    <v-container>
      <div class="skill-header">
        <span><h3><v-icon style="color: #ff4a57 !important;">mdi-lightbulb</v-icon> <span class="skills-adjust"></span></h3></span>
      </div>

      <hr style="color: #888ba5 !important" />
      <div>
        <p>
          As someone who is interested in machine learning and data science, I am drawn to the potential of using data to solve real-world problems and make a positive impact in fields such as healthcare,
           education, and finance. Additionally, I find the intellectual challenge and curiosity of understanding and working with complex data and algorithms to be very rewarding. I believe that the skills and knowledge I will gain through studying machine learning and data science will not only be personally fulfilling, but also highly valuable in the job market. 
          Overall, I am passionate about pursuing a career in these fields and believe that they offer limitless potential for growth and advancement.
        </p>
       
      </div>
    </v-container>
   <div class="pb-15">
    
   </div>
  </div>
 
 
</template>
<script>
import About from "../components/About.vue";

export default {
  componets: {
    About,
  },

  data() {
    return {
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
    };

  },
};
</script>
<style scoped>
.name-header h1, h5
{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: white;
}
.icon-color .v-btn
{
  background-color: transparent !important;
  color: white !important;
  border: 1px solid #fe4b57;
}
.icon-color .v-btn:hover
{
  background-color: white !important;
  border: 1px solid #fe4b57;
  color: #fe4b57 !important;
}
.icon-color a {
  text-decoration: none !important;
}
.v-card {
  background: #35394e;
  margin-bottom: 1rem;
  border-radius: 10px;
  padding-top: 15px;
 color: white;
}
.skill-header {
  color: #6c6c69 !important;
  margin-bottom: 1rem !important;
}

.skill-container
{
  background-color: #d9d9e0;
   
}
.work-experience
{
  margin-top: 2rem;
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

.v-container
{
  background-color: #2d3047;
  margin-top: 5rem;
  border-radius: 10px;
  margin-bottom: 2em;
  color: white;
}

.skills
{
  padding-bottom: 10px;
  margin-bottom: 1em;
}
.v-layout p {
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
}
.v-btn {
  background: #ff4a57 !important;
  color: white !important;
 
 
}
.v-btn:hover {
  background: #888ba5 !important;
  color: white !important;
}

.education {
  display: flex;
  flex-direction: row;
  width: 100%;
  text-align: center;
}
.v-card:hover
{
  background: #202236 !important;
  cursor: pointer;
  color: white !important;
}
.card {
  display: flex;
  flex-direction: column;
}

.card-image {
  width: 100%;
  max-width: 300px;
}

.card-text {
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
}

img {
  width: 100%;
  height: auto;
  opacity: .7;
  
}


.hidden-sm-and-down {
  display: none;
}
@media (min-width: 960px) {
  .hidden-sm-and-down {
    display: block;
  }
}

.hidden-md-and-up {
  display: block;
}


@media (min-width: 960px) {
  .hidden-md-and-up {
    display: none;
  }
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
