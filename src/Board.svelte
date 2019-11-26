<script>
import Cyan from './Cyan.svelte';
export let show;
import image from "../img/dell-logo-clipart-transparent-8.svg"

</script>

<style>

div.board{
  color: white;
	display: flex;
	font-size: calc(9px + 0.25vw);
	padding: 0.5rem;
	position: relative;
}

div.board > img{
  max-width: 200px;
	padding: 0.5rem;
	width: 100%;
  filter: invert(100%) sepia(6%) saturate(0%) hue-rotate(115deg) brightness(108%) contrast(108%);


}

div.board > ul{
  list-style: none;
	padding: 0;
	margin: 0 0 0 0.5rem;
}

div.boardHidden{
    color: black;
	display: none;
	font-size: calc(9px + 0.25vw);
	padding: 0.5rem;
	position: relative;
}

</style>
{#if show }
    <div class="board">
        <img src={image} alt="Dell system logo">
        <ul class="boardList">
          <li>
            <Cyan text="_ubben" />
@
            <Cyan text="codepen" />
          </li>
          <li>-----------------</li>
          <li>
            <Cyan text="OS" />
: Windows 10 - 64 bits
          </li>
          <li>
            <Cyan text="Host" />
: MSDEUS.SITE
          </li>
          <li>
            <Cyan text="Kernel" />
: 4.20.69-nice
          </li>
          <li>
            <Cyan text="Uptime" />
: 7 days, 10 hours, 15 mins
          </li>
          <li>
            <Cyan text="Packages" />
: 22
          </li>
          <li>
            <Cyan text="Shell" />
: bash 5.0.3
          </li>
          <li>
            <Cyan text="Resolution" />
: SMALLxSMALL
          </li>
          <li>
            <Cyan text="Terminal" />
: molin
          </li>
          <li>
            <Cyan text="CPU" />
: Intel i5-7300HQ (4) @ 3.50GHz
          </li>
          <li>
            <Cyan text="GPU" />
: Nvidia Geforce GTX 1050
          </li>
          <li>
            <Cyan text="Memory" />
: 8192MiB / 4096MiB
          </li>
        </ul>
      </div>
{ :else }
    <div class="empty"></div>

{/if}
