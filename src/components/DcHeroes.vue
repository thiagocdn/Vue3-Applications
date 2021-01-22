<template>
  <div class="m-auto">
    <h1 class="text-3xl text-center">Dc Heroes: {{ heroesCount }}</h1>
    <ul>
      <li class="flex justify-between" v-for="(heroe, index) in dcHeroes" :key="heroe.name">
        <p>{{heroe.name}}</p>
        <button @click="removeHero(index)">x</button>
      </li>
    </ul>
    <form class="mt-10" @submit.prevent="addHero">
      <input class="border rounded-lg" v-model.trim="newHero" placeholder="Type Hero name">
      <button class="border rounded bg-gradient-to-t from-blue-700 to-green-500 text-white" type="submit">Add Hero</button>
    </form>
    <small>Total heroes in the list is {{heroesCount}}</small>
  </div>
</template>

<script>
export default {
  
  computed: {
    heroesCount() {
      return this.dcHeroes.length;
    },
  },
  methods: {
    addHero() {
      if(this.newHero !== '') {
        this.dcHeroes.push({ name: this.newHero });
        this.newHero='';
      }
    },
    removeHero(index) {
      this.dcHeroes = this.dcHeroes.filter((hero, i) => i !== index);
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