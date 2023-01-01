<template>
  <div class="container">
    <About/>
    <v-cantainer>
      <v-row class="work-experience"> 
        <v-col cols="12" md="6" lg="4" xl="3">
              <img src="/profile-pic.png" alt="Card image" />
        </v-col>
        <v-col cols="12" md="12" lg="6" xl="3">
          <div class="text-center name-header pt-3">
            <h1>Isaac Ike Mhlanga</h1>
            <h5>Software developer</h5>
        <div class="pt-1">
          <span style="color: #fe57c0">
            <v-icon class="mx-0">mdi-phone</v-icon>
            +27 671004050
          </span>
          <span style="color: #fe57c0">
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
              <v-btn
              v-for="icon in icons"
              :key="icon"
              color="grey"
              class="mx-2 btn-radius"
              :icon="icon"
              size="small"
            ></v-btn>
            </div>
        </v-col>
      </v-row>
    </v-cantainer>
    <v-container class="skill-container" app>
      <div class="skill-header">
        <span><h3><v-icon style="color: #fe4b57 !important;">mdi-lightbulb-on</v-icon></h3></span>
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
        <v-btn class="text-caption">Go to skills</v-btn>
      </div>
      <v-row class="work-experience pt-3"> 
        <v-col cols="12" md="6" lg="4" xl="3">
          <v-card elevation="9">
            <v-card-text>
              <p>-Experience working with HTML5</p>
              <p>-Experience working with CSS3</p>
              <p>-Experience working with Javascript</p>
              <p>-Experience working with git and github</p>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="6" lg="4" xl="3">
          <v-card elevation="9">
            <V-card-text>
              <p>-Experience working with java</p>
              <p>-Experience working with c++</p>
              <p>-Experience working with c#</p>
              <p>-Experience working with Node.JS</p>
            </V-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="6" lg="4" xl="3">
          <v-card elevation="9">
            <v-card-text>
              <p>-Experience working with laravel</p>
              <p>-Experience working with Vue.js</p>
              <p>-Experience working with PHP</p>
              <p>-Experience Working with SQL</p>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <v-container>
      <div class="skill-header">
        <h3><v-icon style="color: #fe4b57 !important;">mdi-briefcase</v-icon></h3>
      </div>

      <hr style="color: #6c6c69 !important" />
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
        <v-btn class="text-caption">Go to projects</v-btn>
      </div>
    </v-container>
    <v-container>
      <div class="skill-header">
        <h3>Interests</h3>
      </div>

      <hr style="color: #6c6c69 !important" />
      <div>
        <p>
          As someone who is interested in machine learning and data science, I am drawn to the potential of using data to solve real-world problems and make a positive impact in fields such as healthcare,
           education, and finance. Additionally, I find the intellectual challenge and curiosity of understanding and working with complex data and algorithms to be very rewarding. I believe that the skills and knowledge I will gain through studying machine learning and data science will not only be personally fulfilling, but also highly valuable in the job market. 
          Overall, I am passionate about pursuing a career in these fields and believe that they offer limitless potential for growth and advancement.
        </p>
       
      </div>
    </v-container>
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
        "mdi-facebook",
        "mdi-twitter",
        "mdi-linkedin",
        "mdi-instagram",
        "mdi-github",
      ],
    };

  },
};
</script>
<style scoped>
.name-header h1, h5
{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #6c6c69;
}
.icon-color .v-btn
{
  background-color: #fe57c0 !important;
  border: 1px solid #fe4b57;
  color: #fedfa5 !important;
}
.icon-color .v-btn:hover
{
  background-color: #fedfa5 !important;
  border: 1px solid #fe4b57;
  color: #fe57c0 !important;
}
.v-card {
  background: #fe4b57;
  margin-bottom: 1rem;
  border-radius: 10px;
  padding-top: 15px;
  color: black !important;
}
.skill-header {
  color: #6c6c69 !important;
  margin-bottom: 1rem !important;
}

.conatiner {
  margin-top: 1rem;
  padding-bottom: 5px !important;
  margin-bottom: 4rem;
 
}
.skill-container
{
   
  background-color: #d9d9e0;
  padding-bottom: 5rem ;
  
}
.work-experience
{
  margin-top: 2rem;
  background-color: #f0f0f5;
  border-top-left-radius: 50%;
  border-bottom-left-radius: 50%;
  border-bottom-right-radius: 50%;
  border-top-right-radius: 50%;
  border: 1px solid #fe57c0;
  box-shadow: 11px 9px 17px 5px rgba(254,87,192,0.73);
-webkit-box-shadow: 11px 9px 17px 5px rgba(254,87,192,0.73);
-moz-box-shadow: 11px 9px 17px 5px rgba(254,87,192,0.73);
}
.v-container
{
  background-color: #f0f0f5;
  margin-top: 5rem;
  border-radius: 10px;
  margin-bottom: 6em;
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
  background: #fe4b57 !important;
  color: white !important;
 
}
.v-btn:hover {
  background: #fe57c0 !important;
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
  background: #fe57c0 !important;
  cursor: pointer;
  color: white;
}
.card {
  display: flex;
  flex-direction: column;
  background: #d9d9e0;
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





</style>
