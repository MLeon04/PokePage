
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
    <div class="p-4" v-if="pokemonInfo">
        <div class="border h-full rounded-2xl p-4">
            <p class="text-center text-2xl">{{ pokemonInfo.name }}</p>
        </div>
    </div>
    <div v-else>Cargando...</div>
</template>