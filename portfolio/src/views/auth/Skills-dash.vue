<template>
<div class="conatiner">
  <NavDash />
  <div class="skills-section">
    <sForm />

    <div class="skills-container">

      <v-card elevation="9" v-for="skill in skills" :key="skill.name">
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
          <v-card-actions>
            <sForm :skill="skill" :index="skill" />
            <v-btn class="mb-2 bg-danger text-white" @click="skillConfirm(skill.id, skill.name)">
              <v-icon>mdi-delete</v-icon>
              <span class="text-caption text-lowercase">Delete</span>
            </v-btn>
          </v-card-actions>
        </div>
      </v-card>

    </div>
    <v-dialog  persistent v-model="deleteDialog" width="400">
      <v-card>
        <v-card-title>Delete Project</v-card-title>
       
        <v-card-text >Are you sure you want to delete <b>{{ sname }}</b></v-card-text>
        <br>
        <v-card-actions class="text-white">
          <v-btn 
          class="bg-danger text-caption"  
          prepend-icon="mdi-delete" 
          :loading = 'isDeleting'
          @click="deleteProject">
          Delete
        </v-btn>
          <v-btn class="bg-secondary text-caption" prepend-icon="mdi-close" @click="deleteDialog= !deleteDialog">Close</v-btn>
        </v-card-actions>

      </v-card>
    </v-dialog>


  </div>
</div>
</template>
<script>
import NavDash from "../../components/NavDash.vue";
import sForm from '../../components/sForm.vue'
import { firestore,  storage, ref,  skills, auth,  getDownloadURL } from "../../Firebase/firebase";
import { uploadBytes } from "firebase/storage"; 
 
export default {
  components: {
    NavDash,
    sForm,
  },
  data() {
    return {
      isDeleting: false,
      deleteDialog: false,
      sid: null,
      sname: null,
      skills: [],
    };
  },

  methods: {
    async onUpload(e) {
      this.isLoading = true;
      let file = e.target.files[0];
      const mountainsRef = ref(storage, file.name);

      let data = {
        imageId: auth.currentUser.uid,
        name: this.title,
        image: mountainsRef.name,
      };

      //save the data on firestore
      const doc = await skills.add(data);

      uploadBytes(mountainsRef, file).then((snapshot) => {
        this.isLoading = false;
        this.dialog = false;
      });
    },

    async getData() {
      firestore
        .collection("skills")
        .get()
        .then((querySnapshot) => {
          querySnapshot.forEach(async (doc) => {
            let img = "";
            if (doc.data().image) {
              const starsRef = ref(storage, doc.data().image);
              getDownloadURL(starsRef).then((url) => {
                img = url
              });
              // img = await storage
              //   .ref()
              //   .child(doc.data().image)
              //   .getDownloadUrl();
            }
            this.skills.push({
              id: doc.id,
              name: doc.data.name,
              imgages: img,
            });
          });
        });
    },

    //delete project 
    async skillConfirm(id, name)
    {
      this.deleteDialog  = true,
      this.sid = id,
      this.sname = name
    },

    //DeLATE SKILL
    async deletesKill()
    {
      try {

        this.isDeleting = true,
        await projects.doc(this.pid).delete()
       
        alert('skill Deleted')
        //remove the project from the array
        this.projects.splice(this.projects.findIndex(x => x.id == this.pid), 1)

        this.sid = null,
        this.sname = null,
        this.isDeleting = false,

        this.deleteDialog = false;
        
      } catch (error) {
        console.log(error)
      }
    }
  },
  mounted() {
    this.getData();
   
    
  },
};
</script>
<style scoped>
.v-card-title {
  text-align: center;
}
.v-btn
{
  width: 80px;
}
.custom-file-upload {
  border-bottom: 1px solid rgb(160, 160, 160);
  padding: 10px;
  cursor: pointer !important;
  color: grey !important;
  margin-bottom: 1em;
}

input[type="file"] {
  display: none;
}
.v-form {
  padding-top: 2em;
  padding-bottom: 1em;
}

.v-container {
  flex-flow: column wrap;
}
.skills-container {
  font-size: 14px;
  font-style: inherit;
}

.skills-container .v-card {
  background: #35394e;
  border-radius: 8px;
  color: rgb(77, 76, 76);
  width: 100% !important;
}

.skills-section {
  padding-top: 20px;
}

.skills-container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  justify-content: center;
  grid-gap: 1rem;
  padding: 5px 30px;
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
</style>
