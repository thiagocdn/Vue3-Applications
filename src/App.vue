<template>
  <h1>Dc Heroes: {{ heroesCount }}</h1>
  <ul>
    <li v-for="(heroe, index) in dcHeroes" :key="index">
      {{heroe.name}}
    </li>
  </ul>
  <form @submit.prevent="addHero">
    <input v-model.trim="newHero" placeholder="Type Hero name">
    <button type="submit">Add Hero</button>
  </form>
  <small>Total heroes in the list is {{heroesCount}}</small>
</template>

<script>
export default {
  computed: {
    heroesCount() {
      return this.dcHeroes.length;
    }
  },
  methods: {
    addHero() {
      if(this.newHero !== '') {
        this.dcHeroes.push({ name: this.newHero });
        this.newHero='';
      }
    },
    removeHero() {

    },
  },
  data() {
    return {
      newHero: "",
      dcHeroes: [
        { name: 'SuperGirl' },
        { name: 'Flash' },
        { name: 'Batman' },
        { name: 'Arrow' }
      ],
    }
  }

}
</script>

<style>

</style>