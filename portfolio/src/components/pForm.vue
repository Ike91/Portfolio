<template>
   <v-layout>
    <v-row>
      <v-col>
        <v-btn class="mb-2 bg-primary"  @click="dialog= !dialog" v-if="!project">
          <v-icon class="mx-1">mdi-plus-box</v-icon>
          <span class="text-caption text-lowercase">Add Project</span>
        </v-btn>
        <v-btn class="mb-2 mr-2 bg-primary" v-else @click="dialog = !dialog">
          <v-icon class="mx-1">mdi-pencil</v-icon>
          <span class="text-caption text-lowercase">Edit Project</span>
        </v-btn> 
      </v-col>
    </v-row>
      <v-dialog v-model="dialog" width="600" >
      <v-row>
        <v-col>
          <v-card>
            <v-card-text>
              <v-card-title class="text-center">Edit Project</v-card-title>
              <v-form ref="pForm">
                <v-text-field
                v-model="name"
                label="Name"
                prepend-icon="mdi-account"
                >
    
                </v-text-field>
    
                <v-textarea
                v-model="discription"
                label="Discription"
                prepend-icon="mdi-pencil"
                >
    
                </v-textarea>
    
                <v-text-field
                v-model="link"
                label="Link"
                prepend-icon="mdi-github"
                >
    
                </v-text-field>
    
                <v-card-actions>
                  <v-btn 
                     class="text-caption ml-8 bg-primary" 
                     prepend-icon="mdi-store"
                     :loading="isSaving"
                     v-if="!project"
                     @click="saveProject"
                     >
                     Save
                  </v-btn>
                  <v-btn 
                     class="text-caption pl-4 ml-8 bg-primary" 
                     prepend-icon="mdi-update"
                     :loading="isUpdating"
                     @click="updateProject(project.id)"
                     v-else
                     >
                     Update
                 </v-btn>
                </v-card-actions>
              </v-form>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-dialog>
   </v-layout>
</template>
<script>
import { auth, projects } from '../Firebase/firebase'
export default {

  name: 'pForm',

   props: ['project', 'index'],

   data(){
    return {
      isSaving: false,
      isUpdating: false,
      dialog: false,
      name: '',
      discription: '',
      link: '', 
      projects: [],
        
    }
   },

methods: {

   //reset the form 
   resetForm() {
      this.$refs.pForm.reset();
    },

   //save project
   async saveProject() {
      this.isSaving = true;

      let data = {
        id: auth.currentUser.uid,
        name: this.name,
        discription: this.discription,
        link: this.link,
       
      };

      //save data on firestore
      const doc = await projects.add(data);

      this.isSaving = false;

      //reset the form
      this.resetForm();
      //close the dialog
      this.dialog = false;
    },

    //update project
    async updateProject(id) {
      this.isUpdating = true;

      let data = {
        id: auth.currentUser.uid,
        name: this.name,
        discription: this.discription,
        link: this.link,
       
      };

      //save data on firestore
      const docRef = projects.doc(id);
      await docRef.update(data);
      
      this.isUpdating = false;

      //reset the form
      this.resetForm();
      //close the dialog
      this.dialog = false;
    },

    //get data.
    async getData() {
      firestore
        .collection("projects")
        .get()
        .then((querySnapshot) => {
          querySnapshot.forEach((doc) => {
            this.projects.push(doc.data());
          });
        });
    },
  },

  mounted()
  {
    if(this.project)
    {
       this.name = this.project.name,
       this.discription = this.project.discription,
       this.link = this.project.link
    }
  }
}
</script>
<style scoped>
.v-card
{
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  background: rgb(219, 210, 210);
}
</style>