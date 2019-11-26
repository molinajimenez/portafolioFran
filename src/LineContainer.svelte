<script>
    import Blinker from './Blinker.svelte';
    export let text;
    export let active = false;
</script>

<style>
    li{
        color: white;
	    margin-top: 0.15rem;
        position: relative;
        list-style: none;
    }
</style>

{#if active }
    <li>${text}<Blinker /></li>
{ :else }
    <li>{text}</li>

{/if}