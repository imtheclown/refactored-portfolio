<link rel="stylesheet" href="assets/auxiliaryStyle.css">
<script setup>
import NavBar from "@/components/NavBar.vue";
import ProjectContainer from "@/components/ProjectContainer.vue";
import EducationContainer from "@/components/EducationContainer.vue";
import AboutMeContainer from "@/components/AboutMeContainer.vue";
import programmingLanguageContainer from "@/components/ProgrammingLanguageContainer.vue";
</script>
<template>
  <body class="body">
  <nav-bar @parent-scroll="ref => {
    this.$refs[ref].scrollIntoView({behavior:'smooth'})
  }" class="navbarAddition">
  </nav-bar>
  <div ref="home" class="backgroundColor section is-large">
    <div class="container has has-text-centered">
      <article class="centerContainer">
        <div>
          <h1 class ="gradientText mainFont">Jonathan Calugas</h1>
          <p class="subtitle  secondaryFont has-text-weight-bold has-text-light">Aspiring Web Developer</p>
        </div>
      </article>
    </div>
  </div>
  <section class="section">
    <div class = "container">
      <div class = "columns is-multiline">
        <div ref = "project" class ="column is-four-fifths-widescreen is-four-fifths-desktop is-fullwidth is-two-thirds-tablet">
          <project-container ></project-container>
        </div>
        <div ref="language" class="column is-one-fifth-widescreen is-one-fifth-desktop is-one-third-tablet">
          <programming-language-container  class="container"/>
        </div>
      </div>
    </div>
  </section>
  <div class="section">
    <div class="container">
      <div class="columns">
        <div ref ="about" class="column is-two-thirds ">
          <AboutMeContainer></AboutMeContainer>
        </div>
        <div ref ="education" class="column is-one-thirds">
          <p class="title mainFont">Education</p>
          <EducationContainer ></EducationContainer>
        </div>
      </div>
    </div>
  </div>
  </body>
</template>
<style lang="scss">
@import "../css/mystyles.css";
@import "./assets/auxiliaryStyle.css";

</style>
