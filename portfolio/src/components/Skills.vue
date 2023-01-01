<template>
  <div class="container">
    <div class="skills-section">
      <div class="skills-header">
        <h1>Skills</h1>
      </div>
      <br />
      <div class="summary text-center">
        <p>
          I aquired these skills through personal projects and practice, and
          from online platforms such as code academy, udemy couses, leetCode just to name a few, it was very
          funny learning them. I have taken it upon myself to stay abreast of
          emerging technologies in computer science, and use this knowledge to
          continue to improve upon my own skills and abilities. I have also been
          able to apply my skills to help CS majors students I have worked with in the
          past. I have done this by understanding their goals and objectives,
          and creating solutions to help them move closer to achieving their
          goals. My ability to think critically and come up with innovative
          solutions has led to me being able to help improve their understanding and their overall performance.
        </p>
      </div>
      <div class="skills-container">
        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://cdn.freebiesupply.com/logos/large/2x/html-5-logo-png-transparent.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>HTML 5</h3>
            </div>
          </div>
        </v-card>

        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://upload.wikimedia.org/wikipedia/commons/3/3d/CSS.3.svg"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>CSS3</h3>
            </div>
          </div>
        </v-card>

        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img src="-" alt="" class="skills-icons" />
              </div>
              <h3>JAVASCRIPT</h3>
            </div>
          </div>
        </v-card>
        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="http://pluspng.com/img-png/nodejs-logo-png-nice-images-collection-node-js-desktop-wallpapers-370.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3 class="text-white">NODE.JS</h3>
            </div>
          </div>
        </v-card>

        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://mildaintrainings.com/wp-content/uploads/2017/11/react-logo.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>REACT</h3>
            </div>
          </div>
        </v-card>

        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://vuejs.org/images/logo.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>Vue.js</h3>
            </div>
          </div>
        </v-card>

        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://2.bp.blogspot.com/-bGTsFydT5d8/WM-Gs0K0FTI/AAAAAAAAFpM/AGJ-DWijk785bQjk9FF99PpcySIrtWHIgCPcB/s1600/laravel_logo.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>Laravel</h3>
            </div>
          </div>
        </v-card>

        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://e7.pngegg.com/pngimages/458/566/png-clipart-web-development-php-computer-icons-ios-logo-blue-text.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>PHP</h3>
            </div>
          </div>
        </v-card>

        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://javascriptforwp.com/wp-content/uploads/2019/03/badge-gatsby.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>GATSBY.JS</h3>
            </div>
          </div>
        </v-card>
        <v-card elevation="9">
          <div class="skills-box">
            <div class="skills-title">
              <div class="skills-img">
                <img
                  src="https://javascriptforwp.com/wp-content/uploads/2019/03/badge-gatsby.png"
                  alt=""
                  class="skills-icons"
                />
              </div>
              <h3>GATSBY.JS</h3>
            </div>
          </div>
        </v-card>
      </div>
      <br />
      <br />
    </div>

    <div class="education">
      <div class="row" style="margin-top: 1em">
        <div class="col-sm-12 col-md-4">
          <div class="bar front expert" data-skill="HTML5"></div>
          <div class="bar front advanced" data-skill="CSS3"></div>
          <div class="bar back basic" data-skill="Jquery"></div>
          <div class="bar back advanced" data-skill="JAVASCRIPT"></div>
        </div>

        <div class="col-sm-12 col-md-4">
          <div class="bar front advanced" data-skill="PHP"></div>
          <div class="bar back intermediate" data-skill="JAVA"></div>
          <div class="bar front expert" data-skill="NODE JS"></div>
          <div class="bar back intermediate" data-skill="C#"></div>
        </div>
        <div class="col-sm-12 col-md-4">
          <div class="bar front advanced" data-skill="LARAVEL"></div>
          <div class="bar back basic" data-skill=".NET Core"></div>
          <div class="bar front expert" data-skill="VUE JS"></div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
};
</script>
<style scoped>
.v-container {
  flex-flow: column wrap;
}
.summary {
  padding-bottom: 2em;
}
.skills-container {
  font-size: 14px;
  font-style: inherit;
}

.skills-container .v-card {
  background: rgb(219, 210, 210);
  border-radius: 8px;
  color: rgb(77, 76, 76);
  width: 100% !important;
}

.skills-section {
  padding-top: 20px;
}

.skills-header {
  text-align: center;
  color: rgb(77, 76, 76);
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  padding: 1rem;
  position: relative;
}
.education {
  margin-bottom: 5em;
  margin-top: 3em;
}
.skills-header:after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background-color: rgb(143, 142, 142);
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  border-radius: 2px;
}

.skills-container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  justify-content: center;
  align-items: center;
  text-align: center;
  grid-gap: 1rem;
  padding: 1rem 80px;
  font-size: 1.2rem;
}
.skills-box {
  color: #000;
  cursor: pointer;
}

.skills-box:hover .skills-img {
  transform: translateX(-20px);
}

.skills-title {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  position: relative;
}

.skills-title:after {
  content: "";
  position: absolute;
  bottom: 0;
  right: 50%;
  width: 20px;
  height: 4px;
  border-radius: 2px 0 0 2px;
  transition: 0.5s;
}

.skills-title:before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 100px;
  height: 4px;
  border-radius: 0 2px 2px 0;
}

.skills-icons {
  width: 50px;
  z-index: 2;
}

.skills-img {
  width: 90px;
  height: 90px;
  position: relative;
  border-radius: 45px;
  background-color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.5s;
}

.skills-img:after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 50%;
  height: 90px;
  background: rgba(165, 165, 165, 0.5);
  border-radius: 45px 0 0 45px;
}
.skills-title h3 {
  color: white;
  margin-top: 0.5rem;
}
@media screen and (max-width: 990px) {
  .skills-container {
    grid-template-columns: repeat(2, 1fr);
    padding: 2rem 50px;
  }
}

@media screen and (max-width: 650px) {
  .skills-container {
    grid-template-columns: 2fr;
    padding: -10em;
  }
}
@media only screen and (max-width: 600px) {
  .container {
    border-radius: 10px !important;
    margin-top: -4em;
  }
}
/*****************************************************************
my skill set
******************************************************************/
.skills-container {
  padding: 20px;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  font-size: 14px;
  font-style: inherit;
}
.skills-container h1 {
  text-align: center;
  color: white;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.skills-container p {
  text-align: center;
  color: white;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 15px;
}
.skills h2 {
  text-align: center;
}

.bar {
  background-color: transparent;
  padding: 2px;
  border-radius: 15px;
  margin-bottom: 5px;
  font-size: 14px;
  color: #fff;
  font-weight: bold;
  text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.5);
}

.bar::before {
  content: attr(data-skill);
  background-color: #141a44;
  display: inline-block;
  padding: 5px 0 5px 10px;
  border-radius: inherit;
  animation: load 2s 0s;
  -webkit-animation: load 2s 0s;
  -moz-animation: load 2s 0s;
  -o-animation: load 2s 0s;
}

.bar.front::before {
  background-color: #834316;
}
.bar.back::before {
  background-color: #23103a;
}

.bar.learning::before {
  width: calc(20% - 10px);
}
.bar.basic::before {
  width: calc(40% - 10px);
}
.bar.intermediate::before {
  width: calc(60% - 10px);
}
.bar.advanced::before {
  width: calc(80% - 10px);
}
.bar.expert::before {
  width: calc(100% - 10px);
}
</style>
