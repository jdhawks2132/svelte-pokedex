<script>
	export let pokemon;
</script>

<a
	class="p-6 bg-gray-100 text-gray-800 text-center rounded-md shadow-sm hover:shadow-md flex flex-col items-center"
	href={`/pokemon/${pokemon.id}`}
>
	<h2 class="uppercase text-2xl">{pokemon.name}</h2>
	<img src={pokemon.image} alt={pokemon.name} class="h-40 w-40" />
</a>
