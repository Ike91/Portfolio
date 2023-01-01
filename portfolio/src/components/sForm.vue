<template>
    <v-layout>
      <v-row>
        <v-col>
          <v-btn class="mb-2 bg-primary ml-8"  @click="skillDialog= !skillDialog" v-if="!skill">
            <v-icon class="mx-1">mdi-plus-box</v-icon>
            <span class="text-caption text-lowercase">Add Skill</span>
          </v-btn>
          <v-btn class="mb-2 bg-primary customBtn" @click="skillDialog= !skillDialog" v-else>
            <v-icon class="">mdi-pencil</v-icon>
            <span class="text-caption text-lowercase">Edit skill</span>
          </v-btn>
        </v-col>
      </v-row>
          <v-dialog v-model="skillDialog" width="600">
          <v-card>
            <v-card-title class="text-center" v-if="!skill">Add skill</v-card-title>
            <v-card-title class="text-center" v-else >Update skill</v-card-title>
            <v-card-text>
              <v-form ref="sForm">
                <v-text-field
                v-model="name"
                prepend-icon="mdi-account"
                label="Name"
                >
                </v-text-field>
        
                <v-text-field
                v-model="image"
                prepend-icon="mdi-camera"
                label="skill imaage"
                >
        
                </v-text-field>
        
                <v-card-actions>
                  <v-btn
                    class="text-caption bg-primary ml-8"
                    prepend-icon="mdi-store"
                    v-if="!skill"
                    @click="saveSkill()">
                   save skill
                  </v-btn> 
        
                  <v-btn
                    class="text-caption bg-primary ml=8"
                    prepend-icon="mdi-update"
                    v-else
                    @click="updateSkill()"> 
                    update skill
                  </v-btn>
                </v-card-actions>
              </v-form>
            </v-card-text>
          </v-card>
         </v-dialog>
       
</v-layout>
</template>
<script>
import { firestore,  storage, ref,  skills, auth,  getDownloadURL } from "../Firebase/firebase";
export default 
{

  props: ['skill', 'index'],
   
    data(){
        return {
        isSaving: false,
        skillDialog: false,
        isUpdating: false,

        name: '',
        image: '',

        skills: [],
        }
    },
    
    methods : {

   //reset the form 
   resetForm() {
      this.$refs.form.reset();
    },

    //save skill
     async saveSkill(e) {
      this.saving = true;
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


    //update skill
    async updateSkill(e) {
      this.isUpdating = true;
      let file = e.target.files[0];
      const mountainsRef = ref(storage, file.name);

      let data = {
        imageId: auth.currentUser.uid,
        name: this.title,
        image: mountainsRef.name,
      };

      //save the data on firestore
      const doc = await skills.doc(skill.id).update(data);

      uploadBytes(mountainsRef, file).then((snapshot) => {
        this.isUpdating = false;
        this.dialog = false;
      });
    },


    //get skill
    async getSkills() {
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
  },

  mounted() {
    this.getSkills(); 
  }
}

</script>
<style scoped>
.v-card
{
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  background: rgb(219, 210, 210);
}
.customBtn .v-btn
{
  width: 80px;
}
</style>