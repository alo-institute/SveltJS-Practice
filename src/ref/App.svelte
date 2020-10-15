<script>

import Greet from './Greet.svelte';
	let name = "Tahuruzzoha Tuhin";
	let greet = "Good Morning";

	// function nameChangedHandler(e){
	// 	name = e.detail;
	// }

</script>
<style>
	div{
		width: 900px;
		min-height: 700px;
		margin: 0 auto;
		background: #ddd;
		font-family: Arial, Helvetica, sans-serif;
		box-sizing: border-box;
		padding: 10px;
	}
	h1{
		
		font-size: 36px;
		text-align: center;
	}
	p{
		font-size: 18px;
		line-height: 1.2;
	}
</style>
<div>
	<h1>
		Hello Svelte , You are  Beauty!
	</h1>
	<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci quis reiciendis blanditiis ducimus architecto vel omnis, nam dolor saepe facere assumenda hic voluptatibus tempore quam necessitatibus sequi enim dolores sed?</p>
	
	<!-- <Greet greet='Welcome' name='Tahuruzzoha Tuhin' on:nameChanged={nameChangedHandler}/> -->
	<Greet greet='Welcome' name='Tahuruzzoha Tuhin' bind:name={name}/>
	<h1>Name: {name}</h1>
</div>