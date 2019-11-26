<script>
import Cyan from './Cyan.svelte';
export let show;

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

</style>
{#if show }
    <div class="board">
        <ul class="boardList">
            <li>
            ===========================================
            </li>
            <li>
                <Cyan text="hobbies" />
                : A small description of my main hobbies.
            </li>
            <li>
                <Cyan text="specs" />
                : The current system I use to work/study.
            </li>
            <li>
                <Cyan text="languages" />
                : The languages I speak.
            </li>
            <li>
                <Cyan text="programming" />
                : The programming languages I have *some* experience with.
            </li>
            <li>
                <Cyan text="social" />
                : My social networks.
            </li>
            <li>
                <Cyan text="currentJob" />
                : Where I'm currently working.
            </li>
            <li>
                <Cyan text="technologies" />
                : Used technologies to create this website.
            </li>
        </ul>
      </div>
{ :else }
    <div class="empty"></div>

{/if}
