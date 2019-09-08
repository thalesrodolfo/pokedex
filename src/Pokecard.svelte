<script>
	export let id;
	export let name;
	export let type;
	export let exp;
	
	const BASE_URL = 
				`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${id}.png`;
</script>

<style>
	.pokecard {
		background-color: #eee;
		border-radius: 10px;
		padding: 20px 8px;
		width: 180px;
		margin: 15px;
		text-align: center;
		box-shadow: 7px 10px 12px -5px #888;
		transition: all .2s ease;
	}
	
	.pokecard:hover {
		cursor: pointer;
		transform: scale(1.1);
	}
	
	.pokecard .name {
		color: blue;
		font-weight: bold;
	}
	
	.pokecard .type, .exp {
		font-size: 80%;
	}
</style>

<div class="pokecard">
	<div class="name">{name}</div>
	<div class="img">
		<img src="{BASE_URL}" alt="{name}"/>
	</div>
	<div class="type">Type: {type}</div>
	<div class="exp">Exp: {exp}</div>
</div>