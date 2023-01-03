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
        
                <label class="btn btn-default btn-file">
                  <span><V-icon class="pr-10" color="white">mdi-paperclip</V-icon></span> <input  type="file" id="file-input">
                </label>
            

                <v-card-actions>
                  <v-btn
                    class="text-caption text-center bg-primary ml-8"
                    prepend-icon="mdi-store"
                    :loading="isSaving"
                    v-if="!skill"
                    @click="saveSkill()">
                    Save
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
import { firestore,  storage, ref,  skills, uploadBytes} from "../Firebase/firebase";
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
      this.isSaving = true;
      const fileInput = document.getElementById('file-input');
      let file = fileInput.files[0];
      const mountainsRef = ref(storage, `skills/` +file.name);

      let data = {
        name: this.name,
        image: file.name,
      };

      //save the data on firestore
      const doc = await skills.add(data).then(function(docRef){
        
        docRef.update({
          id: docRef.id
        })
      });

      uploadBytes(mountainsRef, file).then((snapshot) => {
        //stop the loader
        this.isSaving = false;
        //close the dialog
        this.skillDialog = false;
      });
    },


    //update skill
    async updateSkill(e) {
      this.isUpdating = true;
     
      //Get the image and delete it, then insert the new image, only if the names are different
      const imageRef = ref(storage, `skills/` +this.image);
      const fileInput = document.getElementById('file-input');
      let file = fileInput.files[0];
      const mountainsRef = ref(storage, 'projects/' + file.name);

      //check if the image you have is the same as the one on databse
      if(this.image !== file.name) {
        //delete and insert new one
        deleteObject(imageRef).then(() => {
    
        }).catch((error) => {
        // Uh-oh, an error occurred!
        });

        let data = {
        name: this.title,
        image: mountainsRef.name,
      };

      //save the data
      //save the data on firestore
      const doc = await skills.doc(skill.id).update(data).then(function(docRef){
        docRef.update({
          imageId: docref.id
        });
      });


      }else
      {
        //leave it as it is and just update the fileds



      }

      let data = {
        name: this.title,
        image: mountainsRef.name,
      };

      //save the data on firestore
      const doc = await skills.doc(skill.id).update(data).then(function(docRef){
        docRef.update({
          imageId: docref.id
        });
      });

      uploadBytes(mountainsRef, file).then((snapshot) => {
        this.isUpdating = false;
        this.skillDialog = !skillDialog;
      });
    },

    //get skill
    async getSkills() {
      firestore
        .collection("skills")
        .get()
        .then((querySnapshot) => {
          querySnapshot.forEach((doc) => {
            this.skills.push(doc.data());
          });
        });
    },
  },

  mounted() {
    this.getSkills(); 
    if(this.skill)
    {
      this.name = this.skill.name,
      this.image = this.skill.image
    }
  }
}

</script>
<style scoped>
.v-card
{
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  background: #35394e;
  color: white;
}
.customBtn .v-btn
{
  width: 80px;
}
input[type="file"]
{
  border-radius: 5px !important;
  margin-left: -1rem;
  border: 1px solid white;
  padding: 5px;
  margin-bottom: 1rem;
 
}
.v-btn
{
  width: 100px;
}

</style>