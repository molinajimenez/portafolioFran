<script>
import Cyan from './Cyan.svelte';
import laravel from "../img/laravel.svg";
import js from "../img/javascript.svg";
import Postgresql from "../img/postgres.svg";
import Micropython from "../img/python.svg";
export let showProgramming;

</script>

<style>

div.board{
    color: white;
	display: flex;
	font-size: 12px;
	padding: 0.5rem;
	position: relative;
}

div.board > ul{
    list-style: none;
	padding: 0;
	margin: 0 0 0 0.5rem;
    word-break: break-all;
}

div.board > img.js{
    max-width: 40px;
    max-height: 40px;
    padding: 0rem;
	width: 100%;
    filter: invert(88%) sepia(37%) saturate(2399%) hue-rotate(344deg) brightness(115%) contrast(94%);
}

</style>
{#if showProgramming }
    <div class="board">
        
        <img class="js" src={js} alt="Js logo">
        <ul class="boardList">
            <li>
                ===========================================
            </li>
            <li>
                <Cyan text="Laravel" />
                : I have worked a few projects like Ringwraps e-commerce.
            </li>
            <li>
                <Cyan text="PostgreSQL" />
                : I have used PostgreSQL in my DB projects.
            </li>
            <li>
                <Cyan text="Micropython - Python" />
                : I have used Python for projects that have 
            </li>
            <li>
            few requirements, also I use Micropython for my IoT projects.
            </li>
            <li>
                <Cyan text="Javascript" />
                : I use JS for web dev. I have experience with React and Svelte!
            </li>
        </ul>
      </div>
{ :else }
    <div class="empty"></div>

{/if}
