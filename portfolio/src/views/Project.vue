<template>
  <v-container>
    <div class="project-section">
      <div class="project-header">
        <h1>Projects</h1>
      </div>
      <div class="container" justify="center">
        <p>
          As a dedicated programmer, I am constantly striving to improve my skills and expand my knowledge of new programming languages. To demonstrate my abilities, 
          I have developed a number of projects that are available for viewing on my GitHub profile. 
          Some of these projects have also been deployed live on the web, giving me hands-on experience with coding conventions, 
          debugging, and the importance of good software engineering practices. 
          I am passionate about using my skills to create functional and innovative projects, 
          and I welcome the opportunity to collaborate and learn from others.
        </p>
      </div>
      <v-row justify-center>
        <v-col>
          <v-card>
            <v-card-text>
             <v-img src="/portfolio.png"></v-img>
            </v-card-text>
            <v-card-title>Portfolio</v-card-title>
           
            <v-card-text>
              <v-divider></v-divider>
              <p>
                I am excited to share with you the portfolio site that I developed using vue.js, vuetify, and vuex. 
                Building this project was a fantastic learning experience, 
                and I enjoyed the process of bringing it to life using these powerful tools. 
                Vue.js is a progressive JavaScript framework that allows for the creation of user interfaces, 
                and vuetify is a component library that provides a wide range of beautifully designed UI elements. 
                I also utilized vuex as my state manager, which helped me to manage the data flow within my application and make it more efficient. 
                If you're interested in seeing the code for this project, you can find it on my GitHub profile. 
                I hope you enjoy exploring my portfolio site and learning more about my skills and experience."
              </p>
            </v-card-text>
            <v-card-actions>

              <a  href="https://github.com/Ike91/Portfolio.git" target="_blank">
              <v-btn  class="ml-2 pl-1 text-caption">
                <span><v-icon class="mr-1">mdi-github</v-icon>See Project</span>
              </v-btn>
            </a>
            </v-card-actions>
          </v-card>
          <section class="testimonial text-center">
            <div class="container">
    
              
                <div id="testimonial4" class="carousel slide testimonial4_indicators testimonial4_control_button thumb_scroll_x swipe_x" data-ride="carousel" data-pause="hover" data-interval="5000" data-duration="2000">
                 
                    <div class="carousel-inner" role="listbox">
                        <div class="carousel-item active">
                            <div class="testimonial4_slide">
                                <img src="./Nomkhosi_maseko.jpg" class="img-circle img-responsive" />
                                <p>
                                    I was an open-distance learning student when I first took up a programming module. I had been vaguely familiar with c++, 
                                    but I had my above fair share of incompetence. I then decide to turn to one of the tutors for help, and I am happy to say
                                    that he has held my hand until the end of the semester. I finished my first programming module with a decent mark,
                                    and really could not have gone through my assignments without Isaac Mhlanga
                                </p>
                                <h4>Nomkhosi Maseko<br>UCT</h4>
                            </div>
                        </div>   
                    </div>
                    
                    <a class="carousel-control-prev" href="#testimonial4" data-slide="prev">
                        <span class="carousel-control-prev-icon" color="#fe4b57"></span>
                    </a>
                    <a class="carousel-control-next" href="#testimonial4" data-slide="next">
                        <span class="carousel-control-next-icon"></span>
                    </a>
                </div>
            </div>
        </section>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      projects: [
        
      ],
    };
  },
};
</script>
<style scoped>

.container {
  margin-bottom: 2em;
  text-align: center !important;
}
.project-header {
  text-align: center;
  color: white;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  padding: 1rem;
  position: relative;
  margin-bottom: 2em;
}
.project-section {
  padding-top: 10px;
  color: white;
}
.project-header:after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background-color: rgb(143, 142, 142);
  border-radius: 2px;
}
.v-card-title
{
   margin-bottom: -1em;
   color: #fe4b57;
}
.v-divider 
{
  background-color: #fe4b57 !important;
  
}
a 
{
  text-decoration: none;
}
.v-card-actions 
{
  margin-top: -1em;
}
.v-btn {
  background: #fe4b57;
  width: 100px;
  margin-bottom: 1em;
  color: azure;
}
.v-card 
{
  background: #35394e;
  color: white;
}
.v-icon {
  color: white !important;
}

.v-img
{
  border-radius: 5px;
}
/*--------------------------------------------------------------
# testimonial
--------------------------------------------------------------*/
.heading {
  text-align: center;
  color: #454343;
  font-size: 30px;
  font-weight: 700;
  position: relative;
  margin-bottom: 50px;
  text-transform: uppercase;
  z-index: 999;
}
.white-heading{
  color: grey;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  margin-top: 1em;
}




 .testimonial {
  margin-top: 1rem;
  min-height: 375px;
  position: relative;
  padding-top: 10px;
  padding-bottom: 0px;
  background-position: center;
  background-size: cover;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
}
#testimonial4 .carousel-inner:hover{
cursor: -moz-grab;
cursor: -webkit-grab;
}
#testimonial4 .carousel-inner:active{
cursor: -moz-grabbing;
cursor: -webkit-grabbing;
}
#testimonial4 .carousel-inner .item{
overflow: hidden;
}

.testimonial4_indicators .carousel-indicators{
left: 0;
margin: 0;
width: 100%;
font-size: 0;
height: 20px;
bottom: 15px;
padding: 0 5px;
cursor: e-resize;
overflow-x: auto;
overflow-y: hidden;
position: absolute;
text-align: center;
white-space: nowrap;

}
.testimonial4_indicators .carousel-indicators li{
padding: 0;
width: 14px;
height: 14px;
border: none;
text-indent: 0;
margin: 2px 3px;
cursor: pointer;
display: inline-block;
background: #fe4b57;
-webkit-border-radius: 100%;
border-radius: 100%;
}
.testimonial4_indicators .carousel-indicators .active{
padding: 0;
width: 14px;
height: 14px;
border: none;
margin: 2px 3px;
background-color: #9dd3af;
-webkit-border-radius: 100%;
border-radius: 100%;
}
.testimonial4_indicators .carousel-indicators::-webkit-scrollbar{
height: 3px;
}
.testimonial4_indicators .carousel-indicators::-webkit-scrollbar-thumb{
background: #fe4b57;
-webkit-border-radius: 0;
border-radius: 0;
}

.testimonial4_control_button .carousel-control{
top: 175px;
opacity: 1;
width: 40px;
bottom: auto;
height: 40px;
font-size: 10px;
cursor: pointer;
font-weight: 700;
overflow: hidden;
line-height: 38px;
text-shadow: none;
text-align: center;
position: absolute;
background: transparent;
border: 2px solid #fe4b57;
text-transform: uppercase;
-webkit-border-radius: 100%;
border-radius: 100%;
-webkit-box-shadow: none;
box-shadow: none;
-webkit-transition: all 0.6s cubic-bezier(0.3,1,0,1);
transition: all 0.6s cubic-bezier(0.3,1,0,1);
}
.testimonial4_control_button .carousel-control.left{
left: 7%;
top: 50%;
right: auto;
}
.testimonial4_control_button .carousel-control.right{
right: 7%;
top: 50%;
left: auto;
}
.testimonial4_control_button .carousel-control.left:hover,
.testimonial4_control_button .carousel-control.right:hover{
color: #000;
background: #fe4b57;
border: 2px solid #fe4b57;
}

.testimonial4_header{
top: 0;
left: 0;
bottom: 0;
width: 550px;
display: block;
margin: 30px auto;
text-align: center;
position: relative;
}
.testimonial4_header h4{
color: #fe4b57 !important;
font-size: 30px;
font-weight: 600;
position: relative;
letter-spacing: 1px;
text-transform: uppercase;
margin-top: 1em;

}

.testimonial4_slide{
top: 0;
left: 0;
right: 0;
bottom: 0;
width: 70%;
margin: auto;
padding: 20px;
position: relative;
text-align: center;
}
.testimonial4_slide img {
  top: 0;
  left: 0;
  right: 0;
  width: 136px;
  height: 136px;
  margin: auto;
  display: block;
  color: #f2f2f2;
  font-size: 18px;
  line-height: 46px;
  text-align: center;
  position: relative;
  border-radius: 50%;
  box-shadow: -6px 6px 6px rgba(0, 0, 0, 0.23);
  -moz-box-shadow: -6px 6px 6px rgba(0, 0, 0, 0.23);
  -o-box-shadow: -6px 6px 6px rgba(0, 0, 0, 0.23);
  -webkit-box-shadow: -6px 6px 6px rgba(0, 0, 0, 0.23);
}
.testimonial4_slide p {
  line-height: 1.4;
  margin: 40px 0 20px 0;
}
.testimonial4_slide h4 {
color: #fe4b57 !important;
font-size: 18px;
font-family: 'Times New Roman', Times, serif;
}

.testimonial .carousel {
padding-bottom:65px;
}
.testimonial .carousel-control-next-icon, .testimonial .carousel-control-prev-icon {
  width: 35px;
  height: 35px;
  color: #fe4b57 !important;
  
}

@media only screen and (max-width: 600px) 
{
  .v-container
  {
    margin-top: -5rem;
  }
}
</style>
