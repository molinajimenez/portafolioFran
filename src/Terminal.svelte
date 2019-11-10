<script>
    import { onMount } from 'svelte';
    import Lines from './Lines.svelte';
    import LineContainer from './LineContainer.svelte';
    import Board from './Board.svelte';
    import HiddenForm from './HiddenForm.svelte';

    
    let commands = ['Hey my creator, molinajimenez did this! 🥰'];
    let input = '';
    let show = false;

    $: input = input;
    $: commands = commands;
    $: show = show;

    function changeDisplay(newDisplay){
        input = newDisplay;
    }

    function clearTerminal(){
        commands = [];
        input = '';
        show = false;   
    }

    function handleSubmit(e){
        e.preventDefault();
		if (input.toLowerCase() === 'clear') {
            console.log("clearing")
			clearTerminal()
        } 
        else if (input.toLowerCase() === 'neofetch') {
            console.log("add new line")
            console.log("display TRUE")
            commands = [...prevState.commands, '$ ' + input];
            show = true;
		} else {
            console.log("add new line: command not found")
            commands: [...prevState.commands, '$ ' + prevState.input + ': command not found'];
		}
    }

    onMount(async () => {
        document.querySelector('input[name="inputConsole"]').focus();
    })


</script>

<style>
    div.terminal{

        background: #198B45;
        border-top: 20px solid #c4c4c4;
        border-radius: .25rem;
        box-shadow: 1px 1px 11px rgba(0, 0, 0, 0.22);
        min-height: 425px;
        max-width: 600px;
        min-width: 450px;
        padding: 0.5rem;
        position: relative;
        width: 100%;

    }
    div.terminal::before {
        background: #747474;
        border-radius: 50%;
        content: "";
        display: block;
        height: 10px;
        position: absolute;
        top: -15px;
        left: 5px;
        width: 10px;
    }  
   
</style>

<div class="terminal" tabIndex={0}>
    <Lines commands={commands} />
        
    <Board show={show} />
    <LineContainer active={true} text={' '+input} />
        
    <HiddenForm handleSubmit={handleSubmit} Onchange={changeDisplay}/>
</div>