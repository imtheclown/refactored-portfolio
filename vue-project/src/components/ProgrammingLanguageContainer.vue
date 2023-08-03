<script>
import ProgrammingLanguage from "@/components/ProgrammingLanguage.vue";
export default {
  components: {ProgrammingLanguage},
  data(){
    return{
      frameworkList : [
        {
          name: "Django",
          type: 1
        },
        {
          name: "ReactJS",
          type: 1
        },
        {
          name: "Flutter",
          type: 1
        }
      ],
      languageList: [
        {name: "Python",
        type: 0
        },
        {
          name: "C",
          type: 0
        },
        {
          name: "C#",
          type: 0
        },
        {
          name: "Java",
          type: 0
        },
        {
          name: "JavaScript",
          type: 0
        },
        {
          name: "Dart",
          type: 0
        },

      ],

    }
  }
}
</script>
<template>
<div class = "column">
  <div class="columns is-mobile is-multiline">
    <div class="column is-full-tablet is-full-widescreen is-half-mobile is-full-desktop">
      <p class="mainFont title is-size-4">Programming Languages</p>
      <div class = "columns is-multiline">
        <programming-language class="column is-narrow" v-for ="language in languageList" :name = language.name :type = language.type :key = language.name></programming-language>
      </div>
    </div>
    <div class= "column is-full-tablet is-full-widescreen is-half-mobile is-full-desktop">
      <p class="mainFont title is-size-4">Frameworks</p>
      <div class = "columns is-multiline">
        <programming-language class="column is-narrow" v-for ="language in frameworkList" :name = language.name :type = language.type :key = language.name></programming-language>
      </div>
    </div>
  </div>
</div>
</template>