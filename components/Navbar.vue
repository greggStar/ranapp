<template>
  <div class="flex w-full relative">
    <div class="flex w-full fixed p-8 text-2xl text-purple-500">
      <nuxt-link to="/" class="flex flex-grow text-4xl font-extrabold">
        Ranapp - Your lists here
      </nuxt-link>
      <nav class="flex ml-auto">
        <nuxt-link to="/" class="mr-2 hover:text-purple-700">
          List
        </nuxt-link>
        <nuxt-link
          :to="{ name: 'event-create' }"
          class="mr-2 hover:text-purple-700"
        >
          Create
        </nuxt-link>
      </nav>
    </div>
    <div class="flex h-full relative p-16"></div>
  </div>
</template>
