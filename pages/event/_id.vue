<template>
  <div
    class="flex flex-col flex-wrap justify-center items-center w-full md:w-1/2 mx-0 md:mx-auto"
  >
    <div class="flex text-5xl font-black text-gray-600 mt-10 mb-4">
      {{ event.title }}
    </div>
    <div class="flex text-sm text-gray-500 mb-4">
      {{ event.time }} on {{ event.date }}
    </div>
    <div class="flex font-semibold text-gray-700">
      Organised by: {{ event.organizer ? event.organizer.name : '' }}
    </div>
    <div class="flex text-gray-700 mb-8">Category: {{ event.category }}</div>

    <div class="flex text-gray-800 text-2xl leading-5">
      {{ event.description }}
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  async fetch({ store, error, params }) {
    try {
      await store.dispatch('events/fetchEvent', params.id)
    } catch (e) {
      error({
        statusCode: 503,
        message:
          'Oooh no, we`re unable to fetch any data for the event #' + params.id
      })
    }
  },
  computed: mapState({
    event: (state) => {
      return state.events.event
    }
  }),
  head() {
    return {
      title: this.event.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'What you need to know about ' + this.event.title
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
