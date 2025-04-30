
<script setup>
    import { NuxtLink } from '#components';
</script>

<template>
    <nav>
        <ul class="flex justify-center gap-4 md:gap-10 border-b-1 p-2">
            <li class="cursor-pointer">
                <NuxtLink :to="{name: 'index'}" active-class="active">Noticias</NuxtLink>
            </li>
            <li class="cursor-pointer">
                <NuxtLink :to="{name: 'usInfo'}" active-class="active">Nosotros</NuxtLink>
            </li>
            <li class="cursor-pointer">
                <NuxtLink :to="{name: 'pokemons'}" active-class="active">Pokemons</NuxtLink>
            </li>
            <li class="cursor-pointer">
                <NuxtLink to="" active-class="active">Contacto</NuxtLink>
            </li>
        </ul>
    </nav>
</template>


<style scoped>
    .active {
        border-bottom: 2px solid rgb(255, 12, 12);
    }
</style>