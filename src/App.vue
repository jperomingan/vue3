<template>
  <h1 class="text-center">Dc Heros {{ herosCount }}</h1>
  <ul>
    <li v-for="(hero, index) in dcHeros" :key="hero.name">
      <div>{{ hero.name }}<button v-on:click="remove(index)">X</button></div>
    <input />
    </li>
  </ul>
  <form @submit.prevent="addHero">
    <input v-model.trim="newHero" placeholder="Type Hero Name Here"/>
    <button type="submit">Add Hero</button>
  </form>
</template>

<script>
export default {
  computed: {
      herosCount(){
          return this.dcHeros.length;
      },
  },
  methods: {
    addHero() {
      if (this.newHero != "") {
          this.dcHeros.unshift({ name: this.newHero });
          this.newHero = "";
      }
    },
    remove(index) {
      this.dcHeros = this.dcHeros.filter((hero, i) => i != index);
  },
},
  data() {
    return {
      newHero: "",
      dcHeros: [
        { name: "SuperGirl" },
        { name: "Flash" },
        { name: "Batman" },
        { name: "Arrow" }
      ],
    }
  }
}
</script>