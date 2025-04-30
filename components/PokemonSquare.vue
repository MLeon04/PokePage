
<script setup>

    import { onMounted, ref } from 'vue';

    const props = defineProps({
        id: {
            type: String,
            required: true
        }
    })

    const pokemonInfo = ref(null);

    const {data,error} = await useFetch(`https://pokeapi.co/api/v2/pokemon/${props.id}`);

    if (!error.value) {
        pokemonInfo.value = data.value;
        console.log("Data received:", pokemonInfo.value);
    } else {
        console.error("Error fetching data:", error.value);
    }

</script>

<template>
    <div class="" v-if="pokemonInfo">{{ pokemonInfo.name}}</div>
    <div v-else>Cargando...</div>
</template>