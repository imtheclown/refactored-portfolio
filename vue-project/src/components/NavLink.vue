<script>
export default {
  name: `NavLink`,
  emits: ['scrollNow'],
  props: {
    navName: String,
    refChar: String
  },
}
</script>

<template>
  <li class ="navbar-item is-tab"  @click = "$emit('scrollNow',this.$props.refChar )">
    <a class=" mainFont is-capitalized" >{{navName}}</a>
  </li>
</template>

<style scoped>

</style>