<script>

export default{
  emits: ['gotoSocial'],
  props: {
    socialData: {
      source : String,
      altText: String,
      name: String,
      link: String,
      id: Number
    }
  }
}
</script>
<template>
  <figure class="socials mx-1" @click="$emit('gotoSocial', this.$props.socialData.id)">
    <img class="64x64px" :src="this.$props.socialData.source" alt="">
  </figure>
</template>