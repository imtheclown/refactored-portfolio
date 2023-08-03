<script>
import ProgrammingLanguage from "@/components/ProgrammingLanguage.vue";
import ProjectContribution from "@/components/projectContribution.vue";
export default {
  name: 'ProjectComponent',
  components: {ProjectContribution, ProgrammingLanguage},
  emits: ['gotoProject'],
  props:{
    project: {
      projectName: String,
      description: String,
      contributions: [String],
      programmingLanguages: [String],
      frameworks: [],
      id: Number
    }
  }
}
</script>
<template>
  <div class="container project" @click = "$emit('gotoProject', this.$props.project.id)">
    <div class="card whiteBackground">
      <div class="card-content">
        <div class="content" >
          <header  class="card-header mainFont lavenderBackground">
            <p class="card-header-title">
              {{project.projectName}}
            </p>
          </header>
          <div class="card-content">
            <div class="content">
              <p class="secondaryFont is-capitalized has-text-weight-bold">description:</p>
              {{project.description}}
            </div>
            <div class="content">
              <p class="secondaryFont is-capitalized has-text-weight-bold">contributions:</p>
              <ul>
                <project-contribution v-for = "contribution in project.contributions" :content = contribution :key="contribution"></project-contribution>
              </ul>
            </div>
          </div>
          <footer class="card-footer cardFooterCenter columns is-multiline mt-1">
            <ProgrammingLanguage class="cardFooterCenter-item column is-narrow"  v-for="language in project.programmingLanguages" :name = language :key = language :type="0">
            </ProgrammingLanguage>
            <ProgrammingLanguage class="cardFooterCenter-item column is-narrow" v-for="framework in project.frameworks" :name = framework :key="framework" :type="1">
            </ProgrammingLanguage>
          </footer>
        </div>
      </div>
    </div>
  </div>
</template>