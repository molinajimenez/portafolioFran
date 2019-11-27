<script>
	import Intro from './Intro.svelte';
	import Terminal from  './Terminal.svelte';
	import { fly } from 'svelte-transitions';
	import picMe from '../img/cv_picture.png';
	import uvg from '../img/download.png';
	import beijing from '../img/beijing.png';
	import german from '../img/logo-von-humbolt-1.png';
	import jiu from '../img/jiujitsu.jpg';
	import intrepid from '../img/intrepid.jpg';
	import kauil from '../img/kauil.jpeg';
	import kauil2 from '../img/kauil2.jpeg';
	import smartco from '../img/smartco.jpeg';
	import nc from '../img/nc.jpg';
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
	img.me{
		border-radius: 80%;
		width: 22vw;
		height: 60vh;
		box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 40px 0 rgba(0, 0, 0, 0.59);
		
	}
	div.inner{
		margin: 0;
	}
	div.contentWrapper{
		background: #f0134d;
		padding: 10vh 6vw;
		border-radius: 1.5%;
		z-index: 100;
		text-align: center;
		
		justify-content: center;
	}

	div.contentWrapperTerm{
		background: #f0134d;
		padding: 10vh 6vw;
		border-radius: 1.5%;
		z-index: 100;
		justify-content: center;
	}
	div.page{
		display: grid;
		grid-template-columns: minmax(80px, 200px) auto;
		grid-template-rows: minmax(100px, 100px) auto;
		align-self: center;
		justify-items: center;
	}

	img.round{
		border-radius: 100%;
	}
	img.round2{
		border-radius: 15%;
	}

	div.page:nth-child(2){
		margin-top: 10px; 
	}

	img{
		width: 140px;
		height: 140px;
	}

	img.hobby{
		width: 200px;
		height: 200px;
		border-radius: 15%;

	}

	img.hobbyBig{
		width: 300px;
		height: 300px;
		border-radius: 15%;

	}
	img.hobbyBig2{
		width: 400px;
		height: 300px;
		border-radius: 15%;
	}

	a i{
		font-size: 32px;
	}

	div.white-div{
		background: white;
		max-width: 30vw;
		text-align: justify;
		margin: 40px 0px;
		padding: 2px 20px;
		border-radius: 5%;
	}

	div.white-div-social{
		background: white;
		max-width: 30vw;
		text-align: center;
		margin: 40px 0px;
		padding: 2px 20px;
		border-radius: 5%;
		
	}
	h1{
		color:white;
	}
	p{
		font-size: 18px;
		font-weight: 500;
		
	}

	h3{
		text-align: center;
	}
	li{
		list-style-type: none;
		list-style: none;
		margin: 0px 15px;
	}

	ul.social{
		display: inline-flex;
		padding: 0;
		
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
	
	<div transition:fly class="contentWrapperTerm">
		<div class="inner" on:click="{focusInput}">
			<Terminal />
		</div>
	</div>

	{:else if isMe}
		<div transition:fly class="contentWrapper">
			<h1>Hey, I'm Francisco Molina!</h1>
			<img class="me" src={picMe} alt="a picture of me">

			<div class="white-div">
				<p>I'm a junior backend developer, I have a few surprises for you in this website!</p>
				<p>I'm a Computer science student, working at Deawebo projects part time as backend developer. I'm an IoT enthusiast, currently in love with ESP32 and Micropython</p>
			</div>

			<div class="white-div-social">
				<h3>Wanna contact me?</h3>
				<p>Follow me on my social media!</p>
				<ul class="social">
					<li><a href="https://github.com/molinajimenez"><i class="la la-github"></i></a></li>
					<li><a href="https://twitter.com/molinajimenez_"><i class="la la-twitter"></i></a></li>
					<li><a href="https://www.facebook.com/molinajimenez01"><i class="la la-facebook"></i></a></li>
				
				</ul>
			</div>
			
		</div>

	{:else if isEducation}
		

		<div transition:fly class="contentWrapper">
			<img class="round" src={uvg} alt="UVG logo">
			<img class="round2" src={german} alt="german institute logo"> 
			<img src={beijing} alt="beijing language and culture university">
			
					
			<div class="white-div">
				<ul>
					<li><h3>🏅🏅🏅</h3></li>
					<li>
						<h3>👨‍💻 Computer Science at UVG 👨‍💻</h3>
					</li>
					<li>
						<h3>📃 A2 Zertifikat at von Humboldt Institute 📃</h3>
					</li>
					<li>
						<h3>📃 Chinese language diploma 📃</h3>
					</li>
					<li>
						<h3>📃 ICT Huawei diploma 📃</h3>
					</li>
				</ul>
			</div> 
		</div>
	{:else if isHobby}
		<div transition:fly class="contentWrapper">
			<h1>Sports</h1>
			<img class="hobby" src={jiu} alt="jiu jitsu training">
			<div class="white-div">
				<h3>I enjoy MMA and Jiu jitsu</h3>	
			</div>
			<h1>Travel</h1>
			<img class="hobbyBig" src={intrepid} alt="jiu jitsu training">
			<div class="white-div">
				<h3>My visit to USS Intrepid in NYC</h3>	
			</div>

			<img class="hobbyBig" src={nc} alt="jiu jitsu training">
			<div class="white-div">
				<h3>My visit to USS North Carolina in Willmington, NC</h3>	
			</div>
			<h1>IoT</h1>
			<img class="hobbyBig" src={kauil} alt="jiu jitsu training">
			<div class="white-div">
				<h3>Second IoT project, featuring a gas leak detector.</h3>	
			</div>
			<img class="hobbyBig" src={kauil2} alt="jiu jitsu training">
			<div class="white-div">
				<h3>Case and assembly of Kauil project</h3>	
			</div>
			<img class="hobbyBig2" src={smartco} alt="jiu jitsu training">
			<div class="white-div">
				<h3>Project Icarus, a Smart CO2 sensor</h3>	
			</div>
		</div>
	{/if}
	

</div>



