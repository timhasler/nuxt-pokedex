<template>
  <div>
<h1 class="text-4xl text-center my-8 uppercase">Welcome to SvelteKit Pokedex</h1>
<input class="rounded-md w-full text-lg p-4 border-2
    border-gray-200" type="text" placeholder="Search for Pokemon" bind:value={searchTerm}>
<div class="py-4 grid gap-4 md:grid-cols-2 grid-cols-1">
// put pokemon here
</div>
</div>
</template>

<script>
export default {}
</script>
