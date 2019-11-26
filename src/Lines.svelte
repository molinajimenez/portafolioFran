<script>
    import LineContainer from './LineContainer.svelte';
    export let commands;
</script>

<style>
    ul{
        list-style: none;
        padding: 0;
        margin: 0;
        color: black;
    }
</style>

<ul>
    {#each commands as line}
        <LineContainer text={line}/>
    {/each}
</ul>