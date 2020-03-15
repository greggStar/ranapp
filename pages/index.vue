<template>
  <div class="flex flex-col flex-wrap items-center w-full">
    <div class="flex text-5xl font-black text-gray-600 my-10">RanApp</div>
    <div class="flex flex-wrap w-full md:w-1/3 mx-auto">
      <EventCard
        v-for="(event, index) in events"
        :key="index"
        :event="event"
        :data-index="index"
      />
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import EventCard from '@/components/EventCard'
export default {
  components: {
    EventCard
  },
  // asyncData({ $axios, error }) {
  //   return $axios
  //     .get('http://localhost:3000/events')
  //     .then((response) => {
  //       return {
  //         events: response.data
  //       }
  //     })
  //     .catch((e) => {
  //       error({
  //         statusCode: 503,
  //         message: 'Unable to fetch events at this time'
  //       })
  //     })
  // },
  async fetch({ store, error }) {
    try {
      await store.dispatch('events/fetchEvents')
    } catch (e) {
      error({
        statusCode: 503,
        message: "Oooh no, we're unable to fetch any data for the events"
      })
    }
  },
  computed: mapState({
    events: (state) => state.events.events
  }),
  head() {
    return {
      title: 'list listings'
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
