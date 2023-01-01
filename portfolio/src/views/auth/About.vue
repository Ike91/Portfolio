<template>
    <div>
      <NavDash />
      <About />

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

        }
    }
}
</script>
<style scoped>

</style>