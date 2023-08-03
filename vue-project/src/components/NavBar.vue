<script>
import NavLink from "@/components/NavLink.vue";
export default {
  name: "NavBar",
  emits: ['parentScroll'],
  components: {NavLink},
  data(){
    return {
      showNav: false,
      listOfNavs:[
        {
          name: "home",
          ref: "home"
        },
        {
          name: "projects",
          ref: "project"
        },
        {
          name: "programming languages",
          ref: "language"
        },
        {
          name: "education",
          ref: "education"
        },
        {
          name: "about me",
          ref: "about"
        }
      ]
    }
  },
}
</script>

<template>
  <nav class = "navbar is-fixed-top is-black is-spaced py-0 is-transparent">
    <div class ="navbar-brand">
      <button :class = "`navbar-burger ${showNav? 'is-active': ''}`" @click ="showNav = !showNav">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
    <div :class="`navbar-menu ${showNav? 'is-active': ''}`">
      <ul class ="navbar-start">
        <NavLink @scroll-now = "neref => {$emit('parentScroll', neref)}" v-for="navLink in listOfNavs" :nav-name = navLink.name :key =navLink.name :ref-char = navLink.ref></NavLink>
      </ul>
    </div>
  </nav>
</template>

<style scoped>

</style>