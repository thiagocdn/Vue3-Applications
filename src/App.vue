<template>
  <h1>Dc Heroes</h1>
  <ul>
    <li v-for="(heroe, index) in dcHeroes" v-bind:key="index">{{index}} - {{heroe.name}}</li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      dcHeroes: [
        { name: 'SuperGirl' },
        { name: 'Flash' },
        { name: 'Batman' },
        { name: 'Arrow' }
      ]
    }
  }

}
</script>

<style>

</style>