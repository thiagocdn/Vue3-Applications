<template>
  <AppHeader />
  <div class="flex w-full">
    <!-- <DcHeroes /> -->
    <Calendar />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader';
// import DcHeroes from './components/DcHeroes';
import Calendar from './components/Calendar';
export default {
  components: {
    AppHeader,
    // DcHeroes,
    Calendar,

  },

}
</script>

<style>

</style>