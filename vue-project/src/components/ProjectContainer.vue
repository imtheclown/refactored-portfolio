<script>
import ProjectComponent from "@/components/ProjectComponent.vue";
let id = 0;
export default {
  components: {ProjectComponent},
  data(){
    return {
      listOfProjects: [
        {
          projectName: 'Project Tugon',
          description: 'A centralized feedback system for public agencies and utilities',
          contributions: [
              'developed the backend logic',
              'contributed in the frontend logic'
          ],
          programmingLanguages: [
              "Python",
              "Javascript"
          ],
          frameworks:[
              "Django", "React"
          ],
          id: id++,
          link: `https://github.com/imtheclown/TugonProject`,
        },
        {
          projectName: "Pokemon Console Game",
          description: "A mimicry of the popular Poke'mon game played using a computer's console",
          contributions: ["Developed the whole project"],
          programmingLanguages: ["Java"],
          frameworks: [],
          id: id++,
          link:`https://github.com/imtheclown/pokemon_console_game`
        },
        {
          projectName: "CODM Loadout System",
          description: "A web application that enables users to create customized loadouts for Call of Duty Mobile",
          contributions: ["Developed the whole project"],
          programmingLanguages: ["Javascript", "HTML", "CSS"],
          frameworks: [],
          id: id++,
          link:`//github.com/imtheclown/CMSC126-SPRINT2`
        }
      ]
    }
  },
  methods: {
    gotoProject(index){
      window.open(this.$data.listOfProjects[index].link)
    }
  }
}
</script>
<template>
  <div>
    <p class="mainFont title">Projects</p>
    <div class = "columns is-multiline">
      <project-component @goto-project="index => {gotoProject(index)}"  v-for="project in listOfProjects" :project = project :key= project.id class ="column is-half-desktop is-one-third-widescreen is-half-tablet"/>
    </div>
  </div>
</template>