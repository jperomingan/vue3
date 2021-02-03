<template>
  <h1>Dc Heros</h1>
  <ul>
    <li v-for="(hero, index) in dcHeros" :key="index">
      {{ index }} : {{ hero.name }}
    </li>
  </ul>
  <input :value="newHero" />
  <button :disabled="isDisabled">Add Hero</button>
</template>

<script>
export default {
  data() {
    return {
      isDisabled: false,
      newHero: "Aquaman, Reloaded",
      dcHeros: [
        { name: "SuperGirl" },
        { name: "Flash" },
        { name: "Batman" },
        { name: "Arrow" }
      ]
    }
  }
}
</script>