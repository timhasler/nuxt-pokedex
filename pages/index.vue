<template>
  <div>
    <h1 class="text-4xl text-center my-8 uppercase">Welcome to SvelteKit Pokedex</h1>
    <input class="rounded-md w-full text-lg p-4 border-2 border-gray-200"
      type="text" placeholder="Search for Pokemon" bind:value={searchTerm}>
    <div class="py-4 grid gap-4 md:grid-cols-2 grid-cols-1">
        <PokeCard 
          v-for="pokemon in allPokemon" 
          :key="pokemon.id"
          :pokemon="pokemon"
        />
    </div>
  </div>
</template>

<script>
import PokeCard from '~/components/PokeCard'

export default {
  components: {
    PokeCard
  },
  
  data() {
    return {
      allPokemon: []
    }
  },
  
  async fetch () {
    const url = `https://pokeapi.co/api/v2/pokemon?limit=151`;
    const res = await fetch(url);
    const data = await res.json();
    const pokemon = await data.results.map((data, index) => ({
      name: data.name,
      id: index + 1,
      image: `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${
        index + 1
      }.png`
    }));
    
    this.allPokemon = pokemon;
  }
}
</script>
