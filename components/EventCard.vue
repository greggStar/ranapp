<template>
  <nuxt-link
    class="flex flex-col w-full border-2 border-purple-200 p-4 mb-4 shadow-lg"
    :to="'/event/' + event.id"
  >
    <div class="flex w-full text-purple-700 mb-2">
      @{{ event.time }} on {{ parasedDate }}
    </div>
    <div class="flex w-full text-2xl font-extrabold text-gray-800 mb-2">
      {{ event.title }}
    </div>
    <div class="flex w-full text-purple-700">
      {{ event.attendees.length }} attending
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    event: Object
  },
  computed: {
    parasedDate() {
      const eventDate = new Date(this.event.date)
      return eventDate.toDateString()
    }
  }
}
</script>
