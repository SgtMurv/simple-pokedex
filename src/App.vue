<template>
  <div id="app">
    <h1 class="heading">(╯°□°)╯︵◓</h1>
    <Pokemon
      v-for="(pokemon, index) in pokemonList"
      :key="index"
      :name="pokemon.name"
      :type="pokemon.type"
    >
    </Pokemon>
  </div>
</template>

<script>
import Pokemon from "./components/Pokemon";
import axios from "axios"; // library to make HTTP requests

export default {
  name: "App",
  components: { Pokemon },
  data: () => {
    return {
      pokemonList: [],
      url: "https://pokeapi.co/api/v2/pokemon?limit=30&offset=151"
    };
  },
  // lifecycle method
  created() {
    // fetch some data from the pokemon api.
    this.getPokemon();
  },
  methods: {
    getPokemon() {
      axios.get(this.url).then(response => {
        this.pokemonList = response.data.results;
      });
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 500px;
}
.heading {
  text-align: left;
  margin-left: 170px;
}
</style>
