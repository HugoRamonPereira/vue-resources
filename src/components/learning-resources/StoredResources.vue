<template>
  <ul>
    <LearningResource v-for='resource in resources' v-bind:key='resource.id' v-bind:title='resource.title'
      v-bind:description='resource.description' v-bind:link='resource.link' />
  </ul>
</template>

<script>
import LearningResource from './LearningResource.vue';

export default {
  inject: ['resources'],
  components: {
    LearningResource
  }
}
</script>

<style>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>