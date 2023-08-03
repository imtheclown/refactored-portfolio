<script>
import photo from "@/assets/images/photo.jpg";
import twitter from "@/assets/SVG/twitter.svg"
import facebook from "@/assets/SVG/facebook.svg"
import github from "@/assets/SVG/github.svg"
import SocialsComponent from "@/components/SocialsComponent.vue";

let count = 0;
export default {
  components: {SocialsComponent},
  data(){
    return{
      photo: photo,
      socials:
      [
        {
          name: "Facebook",
          source: facebook,
          altText: "Facebook image",
          link:`https://www.facebook.com/jason.argos.14/`,
          id: count++
        },
        {
          name: "Twitter",
          source:twitter,
          altText: "Twitter image",
          link: `https://twitter.com/cryomumma`,
          id: count++
        },
        {
          name: "Github",
          source: github,
          altText: "Github image",
          link: `https://github.com/imtheclown`,
          id: count++
        }
      ],
      description:"I am an incoming 4th year Bachelor of Science in Computer Science student at the University of the Philippines in the Visayas. " +
          "My theoretical and empirical knowledge makes me suitable for backend development. My passion for programming stemmed due to my love for " +
          "playing video games"
    }
  },
  methods: {
    gotoSocials(index){
      window.open(this.$data.socials[index].link)
    }
  }
}
</script>
<template>
  <div class="container">
    <p class="title mainFont">About Me</p>
    <div class="columns centerContainer is-multiline">
      <div class="column is-one-third is-full-mobile">
        <figure class="m-auto image">
          <img class="my-image m-auto is-rounded" :src="photo" alt="Image Here">
        </figure>
      </div>
      <div class="column is-two-thirds is-full-mobile">
        <p class="content contentFont">{{description}}</p>
      </div>
    </div>
    <footer class="centerContainer">
      <div class="container">
        <p class="secondaryFont flex-justified">Reach me:</p>
        <div class="flex-justified my-2">
          <figure class="centerContainer mx-1">
            <socials-component @goto-social="index => {gotoSocials(index)}" v-for="social in socials" :social-data = social :key = "social.id"></socials-component>
          </figure>
        </div>
      </div>
    </footer>
  </div>
</template>