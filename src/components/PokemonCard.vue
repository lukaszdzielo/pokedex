<script setup lang="ts">

interface PokemonType {
  type: {
    name: string;
  };
}

interface Pokemon {
  name: string;
  imgs: { img: string }[];
  types: PokemonType[];
}

defineProps<{
  pokemon: Pokemon;
}>()

</script>

<template>
    <div>
        <img :src="pokemon.imgs[0].img" :alt="pokemon.name" loading="lazy">
    </div>
    {{ pokemon.name }}
    <ul>
        <li v-for="type in pokemon.types" :key="type.type.name">{{ type.type.name }}</li>
    </ul>
</template>