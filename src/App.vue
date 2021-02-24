<template>
  <div id="app">
    <h1>Characters</h1>
    <characters-list :characters="characters"></characters-list>
    <character-detail :character='selectedCharacter'></character-detail>
  </div>
</template>

<script>
import CharactersList from './components/CharactersList.vue';
import CharacterDetail from './components/CharacterDetail.vue';

import { eventBus } from './main.js';


export default {
  name: 'App',
  data() {
    return {
      characters: [],
      selectedCharacter: null
    };
  },

  mounted() {
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characters = characters.results)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })
  },

  components: {
  "characters-list": CharactersList,
  "character-detail": CharacterDetail,
  }
}

</script>

<style>

</style>