
<script setup>

    import pokemonNews from '~/server/pokemonList.json';
    import CristalCard from '~/components/CristalCard.vue';
    import PokemonNew from '~/components/PokemonNew.vue';
    definePageMeta({
        layout:'default'
    })

</script>

<template>
    <div class="container-full">
        <div class="backImage1 flex items-end">
            <CristalCard/>
        </div>
        <div>
            <p class="text-red-500 flex justify-center text-4xl mt-2 mb-2">Nuevas Noticias</p>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4  mb-6 px-4">
                <PokemonNew v-for="pokeNew in pokemonNews" :pokeNew="pokeNew"/>
            </div>
        </div>
    </div>
</template>