<template>
  <div class="flex flex-wrap justify-center w-full">
    <div class="flex text-5xl font-black text-gray-600 mt-10">
      Create a list item
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'create a list',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Where you can create grand lists'
        }
      ]
    }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
