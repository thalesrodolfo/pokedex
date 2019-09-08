<script>
	import Pokedex from './Pokedex.svelte';
	
	let pokemons = [
		{id: 4, name:'Charmander', type: 'fire', base_experience: 62},
		{id: 7, name:'Squirtle', type: 'water', base_experience: 63},
		{id: 11, name:'Metapod', type: 'bug', base_experience: 72},
		{id: 12, name:'Butterfree', type: 'flying', base_experience: 178},
		{id: 25, name:'Pikachu', type: 'eletric', base_experience: 112},
		{id: 39, name:'Jigglypuff', type: 'fairy', base_experience: 95},
		{id: 94, name:'Gengar', type: 'poison', base_experience: 255},
		{id: 133, name:'Eevee', type: 'normal', base_experience: 65},
	];
	
	var hand1 = [];
	var hand2 = [];
	
	while (hand1.length < 4) {
		var indexR = Math.floor((Math.random() * 6) + 1) -1;
		var pokemon = pokemons[indexR];
		
		if (!hand1.includes(pokemon)) {
			hand1.push(pokemon);
		}
	}
	
	for (var p of pokemons) {
		if (!hand1.includes(p)) {
			hand2.push(p);
		}
	}
	
	var totalHand1 = -1;
	var totalHand2 = -1;
	
	for (var p of hand1) { totalHand1 += p.base_experience; }
	for (var p of hand2) { totalHand2 += p.base_experience; }
	
</script>

<Pokedex pokemons="{hand1}" isWinner="{totalHand1 > totalHand2}" total="{totalHand1}" />
<Pokedex pokemons="{hand2}" isWinner="{totalHand2 > totalHand1}" total="{totalHand2}"/>
