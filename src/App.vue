<script setup lang="ts">
import { onMounted, ref } from 'vue'
import PokemonCard from './components/PokemonCard.vue';

const pokemonList = ref<Array<{ id: number; names: [{ name: string; lang: { code: string}}] }>>([])

const getAllPokemonList = async () => {
  try {
    const res = await fetch('https://beta.pokeapi.co/graphql/v1beta', {
      method: 'POST',
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify({
        query: `{
          data: pokemon_v2_pokemon (
              where: {is_default: {_eq: true}, order: {_gt: 0}}
              order_by: {id: asc}
            ) {
            id
						name 
            imgs: pokemon_v2_pokemonsprites(where: {sprites: {_cast: {}}}) {
              img: sprites(path: "front_default")
            }
            types: pokemon_v2_pokemontypes {
              type: pokemon_v2_type {
                name
              }
            }
          }
        }`
      })
    })
    const json = await res.json();
    console.log('Pokémon list:', json.data.data[0]); 
    return [...json.data.data];
  } catch(e) {
    console.error('Error fetching Pokémon list:', e);
    return [];
  }
};

onMounted(async () => {
  pokemonList.value = await getAllPokemonList();
})
</script>

<template>
  <div v-if="pokemonList.length">
    <h2>Pokémon List</h2>
    <div v-for="pokemon in pokemonList" :key="pokemon.id">
			<PokemonCard :pokemon="pokemon" />
    </div>
  </div>
</template>

<style scoped>

</style>
