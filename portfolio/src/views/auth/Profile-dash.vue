<template>
  <v-container>
    <NavDash/>
    <About/>
  </v-container>
</template>
<script>
import NavDash from "../../components/NavDash.vue";
import About from "../../components/About.vue";
export default{
  components:
  {
    NavDash,
    About,
  }
}
</script>
