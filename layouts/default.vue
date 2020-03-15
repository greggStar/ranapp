<template>
  <div id="app" class="flex flex-wrap w-full">
    <nav-bar />
    <nuxt />
  </div>
</template>

<script>
import NavBar from '~/components/Navbar'
export default {
  components: {
    NavBar
  },
  head() {
    return {
      titleTemplate: '%s - RanApp',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Where you can find and view lists'
        }
      ]
    }
  }
}
</script>

<style>
html {
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
}
</style>
