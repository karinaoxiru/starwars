<template>
    <h1>Personagens StarWars</h1>
  <div v-for="character in characters" :key="character.name">{{ character.name }}>
    <CharacterCard :name="character.name" :height="character.height" :mass="character.mass" />
</div>
</template>
  
  <style scoped></style>
<script setup>
import { ref, onMounted } from 'vue';

const characters = ref([]);
const fetchCharacters = async () => {
  try {
    const response = await fetch('https://swapi.dev/api/people/');
    const data = await response.json();
    characters.value = data.results;
  } catch (error) {
    console.error('Error fetching characters:', error);
  }
};

onMounted(() => {
  fetchCharacters();
});

defineProps({
  name: String,
  height: String,
  mass: String,
});

const CharacterCard = (props) => {
  return {
    name: props.name,
    height: props.height,
    mass: props.mass,
  };
};
</script>

<style scoped>
</style>
