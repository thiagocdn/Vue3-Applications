<template>
  <AppHeader />
  <div class="flex w-full">
    <router-view></router-view>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader'; 
export default {
  components: {
    AppHeader,
  },

}
</script>

<style>

</style>