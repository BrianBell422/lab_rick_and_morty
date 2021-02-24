<template lang="html">
    <div>
        <!-- <ul>
            <list-item v-for="(character, index) in characters" :character="character" :key="index"></list-item>
        </ul> -->
        <label for="character_select">Select a Character:</label>
        <select id="character_select" v-model="selectedCharacter">
            <option disabled value="">Select a character</option>
            <option v-for="(character, index) in characters" :key="index" :character="character">{{character.name}}</option>
        </select>
    </div>
</template>

<script>
import ListItem from './ListItem.vue';

export default {
    name: 'characters-list',
    props: ['characters'],
    components: {
        "list-item": ListItem
    }
}
</script>

<style>

</style>