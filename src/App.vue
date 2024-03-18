<template>
  <TheHeader title='Remember Me' />
  <TheResources />
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import TheResources from './components/learning-resources/TheResources.vue';

export default {
  components: {
    TheHeader,
    TheResources
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Play:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Play', sans-serif;
}

body {
  margin: 0;
  padding: 0;
}
</style>