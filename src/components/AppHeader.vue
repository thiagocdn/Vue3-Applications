<template>
  <nav class="w-full text-white px-4 py-2 bg-gradient-to-r from-blue-800 to-blue-600">
    <router-link
      v-for="item in list"
      :key="item.to"
      :to="item.to"
      class="mx-2 font-bold" 
    >
      {{item.title}}
    </router-link>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      list: [
        { title: 'Home', to: '/'},
        { title: 'Dc Heroes', to: '/dc-heroes'},
        { title: 'Calendar', to: '/calendar'},
        { title: 'Markdown', to: '/markdown'},
      ]
    }
  }
}
</script>

<style>

</style>