<template>
    <ul>
    <LeareningResource
      v-for="resource in resources"
      :key="resource.id"
      :title="resource.title"
      :description="resource.description"
      :link="resource.link"
    >
      {{ resource }}</LeareningResource
    >
  </ul>
</template>

<script>
import LeareningResource from "./LeareningResource"
export default{
    components:{
        LeareningResource
    },
    inject:['resources']
}
</script>

<style scoped>

ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>