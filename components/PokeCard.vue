<template>
    <div class="list-none p-6 bg-gray-100 text-gray-800 text-center rounded-md shadow-sm hover:shadow-md flex flex-col items-center">
        <img class="h-40 w-40 " :src="pokemon.image" :alt="pokemon.name" />
        <h2 class="uppercase text-2xl">{{ pokemon.id }}:  {{ pokemon.name }}</h2>
    </div>
</template>

<script>
    export default {
        props: {
            pokemon: {
                default: () => {},
                type: Object
            }
        }
    }
</script>§