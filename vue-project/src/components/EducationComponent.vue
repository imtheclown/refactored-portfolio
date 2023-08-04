<script>
export default{
  name: "EducationComponent",
  props: {
    education:{
      school: String,
      address: String,
      program: String,
      year: String
    }
  }
}
</script>

<template>
  <div class="card">
    <header class="card-header lavenderBackground">
      <p class ="card-header-title secondaryFont">{{education.school}}</p>
    </header>
    <div class="card-content">
      <p>{{education.program}}</p>
      <p>({{education.year}})</p>
    </div>
  </div>
</template>