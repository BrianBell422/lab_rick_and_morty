<template>
    <div>
        <div v-if='!character'>
            <h3>Please pick a character</h3>
        </div>
        <div v-if='character'>
            <h3>{{character.name}}</h3>
            <p>Species: {{character.species}}</p>
            <p>Status: {{character.status}}</p>
        </div>
    </div>
</template>


<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>


<style>

</style>