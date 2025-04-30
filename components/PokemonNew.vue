

<script setup>
    // const props = defineProps({
    //     pokeNew: {
    //         type: Object,
    //         required: true
    //     }
    // })
    defineProps(['pokeNew']);


    const visibleVal = ref(false);
    const activeFunc = ref(0);

    const isVisible = () => {
        if(!activeFunc.value) {
            visibleVal.value = true;
            activeFunc.value = 1;
        } 
        console.log(visibleVal.value)
    }

    const noneVisible = () => {
        if(activeFunc.value) {
            visibleVal.value = false;
            activeFunc.value = 0;
        }
        console.log(visibleVal.value);
    }

    const visiblesFunctions = (num) => {
        if(num === 0) {
            isVisible();
        } else {
            noneVisible();
        }
    }

</script>


<template>
    <div class="cursor-pointer">
        <div :class="`w-auto h-100 bg-no-repeat bg-cover bg-center`" :style="`background-image: url('images/${pokeNew.imageTitle}.jpg');`">
            <!-- <img :src="`/images/${pokeNew.imageTitle}.jpeg`" :alt="`Noticia Numero ${pokeNew.id}`"  class="w-40 h-40"> -->
            <!-- <NuxtImg :src="`images/${pokeNew.imageTitle}.jpeg`" :alt="`Noticia Numero ${pokeNew.id}`" class="imageW"  /> -->

            <div class="h-100 w-auto" v-on:mouseenter="visiblesFunctions(0)" v-on:mouseleave="visiblesFunctions(1)">
                <div class="backdrop-blur-xs h-100 w-auto p-6 flex justify-center items-center flex-col" v-if="visibleVal">
                    <p class="text-2xl text-red-500 text-center">{{ pokeNew.description }}</p>
    
                    <p class="text-2xl text-center text-white">{{ pokeNew.infoNew }}</p>

                    <div class="flex justify-center mt-2">
                        <NuxtLink to="" class="w-30 h-10 border bg-red-500 text-white text-center flex items-center justify-center rounded-2xl hover:bg-red-600">Ver Noticia</NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style>
    .imageW {
        max-width: 100%;
        height: 100%;
        width: 100%;
    }
</style>