<template>
    <div class="img-center">
        <section class="cards"  v-if="!isLoading">
            <Character 
                v-bind:character="character" 
                v-bind:key="character.id" 
                v-for="character in (filteredCharacters.length > 0 ? filteredCharacters : characters)" 
                v-on:popup="popup"
            />
        </section>
        <img src="../assets/spinner.gif" alt="Loading..." v-else />

    </div>
</template>

<script>

import Character from './Character'

export default {
    name: 'Characters',
    props: ['characters', 'filteredCharacters', 'isLoading', 'popup'],
    components: {
        Character,
    }
}
</script>

<style>

</style>