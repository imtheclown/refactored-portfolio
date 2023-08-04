<script>
import EducationComponent from "@/components/EducationComponent.vue";
export default{
  components: {EducationComponent},
  data(){
    return {
      education :
      [
        {
          school: "University of the Philippines Visayas",
          address: "Miagao, Iloilo",
          program: "BS Computer Science",
          year: "2020-present"
        }
      ]
    }
  }
}
</script>
<template>
  <div class="container">
    <education-component v-for="entries in education" :education = "entries" :key="entries.school"/>
  </div>
</template>