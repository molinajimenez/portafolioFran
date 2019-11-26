<script>
	import Intro from './Intro.svelte';
	import Terminal from  './Terminal.svelte';
	import { fly } from 'svelte-transitions';
	let isMe = true, isTerminal = false, isHobby = false, isEducation = false;

	function focusInput(e){
		document.querySelector('input[name="inputConsole"]').focus()
	}

	function upTransition(params){
		return{
			duration: params.duration || 200,
			css: t => `
				transform: translateY(${t-.5})px;
				opacity: ${1-t};
			
			`
		}
	}
	
</script>

<style>

	div.inner{
		margin: 0;
	}
	div.contentWrapper{
		background: #f0134d;
		padding: 10vh 6vw;
		border-radius: 1.5%;
		z-index: 100;
	}
	div.page{
		display: grid;
		grid-template-columns: minmax(80px, 200px) auto;
		grid-template-rows: minmax(100px, 100px) auto;
		align-self: center;
		justify-items: center;
	}

	div.page:nth-child(2){
		margin-top: 10px; 
	}
	h1{
		color:white;
	}
</style>

<div class="page">
	<section style="position:relative;">

		<Intro 
			bind:isTerminal={isTerminal} 
			bind:isHobby={isHobby}
			bind:isEducation={isEducation}
			bind:isMe={isMe}  
		/>

	</section>


	<section>
	
		<h1>Francisco Molina</h1>
	
	</section>

	<div></div>

	{#if isTerminal}
	
	<div transition:fly class="contentWrapper">
		<div class="inner" on:click="{focusInput}">
			<Terminal />
		</div>
	</div>

	{:else if isMe}
		<div class="inner">
			<p>This is the ME section</p>
		</div>

	{:else if isEducation}
		<div class="inner">
			<p>This is the EDUCATION section</p>
		</div>
	{:else if isHobby}
		<div class="inner">
			<p>This is the HOBBY section</p>
		</div>
	{/if}
	

</div>



