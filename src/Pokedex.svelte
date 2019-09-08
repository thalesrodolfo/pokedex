<script>
	import Pokecard from './Pokecard.svelte';
	
	export let pokemons;
	export let isWinner;
	export let total;
	
	function getId (id) {
		const tamId = id.toString().length;
		if (tamId < 2) {
			return "00" + id.toString();
		} else if (tamId < 3) {
			return "0" + id.toString();
		} else {
			return id.toString();
		}
	}
</script>

<style>
	.pokedex .cards {
		display: flex;
		flex-wrap: wrap;
	}
	
	.pokedex .winner {
		color: green;
	}
	
	.pokedex .loser {
		color: red;
	}
	
	.pokedex .title {
		color: #aaa;
		text-align: center;
	}
</style>

<div class="pokedex">
	<div class="title">
		<h2>
			Pokedex
		</h2>
		<h3 class="{isWinner ? 'winner' : 'loser'}">
			{isWinner ? "Winner" : "Loser"}
			Total: {total}
		</h3>
	</div>
	<div class="cards">
		{#each pokemons as pokemon}
			<Pokecard id={pokemon.id}
							name={pokemon.name}
							type={pokemon.type}
							exp={pokemon.base_experience}
							/>
		{/each}
	</div>
</div>