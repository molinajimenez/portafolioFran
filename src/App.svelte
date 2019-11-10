<script>
	import Intro from './Intro.svelte';
	import Terminal from  './Terminal.svelte';
	export let name;


	function focusInput(e){
		document.querySelector('input[name="inputConsole"]').focus()
	}
</script>

<style>

	div.page{
		display: grid;
		grid-template-columns: minmax(80px, 300px) auto;
		grid-template-rows: minmax(100px, 100px) auto;
		align-self: center;
		justify-items: center;
	}

	div.page:nth-child(2){
		margin-top: 10px; 
	}
	div.content{
		
	}
	h1{
		color:white;
	}
</style>

<div class="page">
	<section style="position:relative;">

		<Intro />

	</section>


	<section>
	<h1>Francisco Molina</h1>
	
	</section>

	<div></div>
	<div class="content">
		<Terminal on:click={focusInput} />
	</div>

</div>



