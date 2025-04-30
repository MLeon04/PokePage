
<script setup lang="ts">

    import { computed, ref } from 'vue';


    const firstId = ref(1);
    // const lastId = ref(12);
    const numloop = ref(12);
    const page = ref(1);

    const changePage = (page:number,type:string) => {

    }

    const getPokemons = async () => {

    }

    const getRange = computed(() => {
        const range = ref<number[]>([]);
        numloop.value = numloop.value * page.value;
        for(let i = 1; i <= numloop.value; i++){
            range.value.push(i)
        }

        return range;
    })

    // onMounted(() => {
    //     changePage(1,'');
    // });


    console.log(getRange.value);

</script>

<template>
    <div>
        <Search/>
    </div>
    <div class="grid grid-cols-4 h-216">
        <PokemonSquare v-for="i in getRange.value" :key="i" :id="i.toString()" />
    </div>
</template>