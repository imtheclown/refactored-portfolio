<script>
export  default {
  // type: 0 for programming language
  // type: 1 for programming frameworks
  props: {
    name: String,
    type: Number,
  },
  computed:{
    determineType()
    {
      return this.$props.type? "fw-gradient":"pl-gradient"
    }
  }
}
</script>
<template>
  <div :class = determineType >
    <p>{{name}}</p>
  </div>
</template>