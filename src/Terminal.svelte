<script>
    import { onMount } from 'svelte';
    import Lines from './Lines.svelte';
    import LineContainer from './LineContainer.svelte';
    import Board from './Board.svelte';
    import BoardHelp from './BoardHelp.svelte';
    import HiddenForm from './HiddenForm.svelte';

    
    let commands = ['Hey, my creator: molinajimenez did this! 🥰'];
    let input = '';
    let show = false;
    let showProgramming = false;
    let showHelp = false;

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
        showProgramming = false;
        showHelp = false;
    }

    function handleSubmit(e){
        e.preventDefault();
		if (input.toLowerCase() === 'clear') {
			clearTerminal()
        } 
        else if (input.toLowerCase() === 'specs') {
            commands = [...commands, '$ ' + input];
            show = true;
        } else if(input.toLowerCase() === 'hobbies') {
            commands = [...commands, '$ ' + "Glad you asked, I enjoy playing videogames and hanging out with my friends 🎈"];
        } else if(input.toLowerCase() === 'languages'){
            commands = [...commands, '$ ' + "I speak Spanish, English and a little bit of German. 📝"];
        } else if(input.toLowerCase() === 'help'){
            commands = [...commands, '$ ' + "Hope this helps 🤓"];
            showHelp = true;
        }
        
        else {
            commands = [...commands, '$ ' + input + ': command not found'];
		}
    }

    onMount(async () => {
        document.querySelector('input[name="inputConsole"]').focus();
    })


</script>

<style>
    div.terminal{

        background: black;
        border-top: 20px solid #c4c4c4;
        border-radius: .25rem;
        box-shadow: 1px 1px 11px rgba(0, 0, 0, 0.22);
        min-height: 425px;
        max-width: 450px;
        min-width: 450px;
        padding: 0.5rem;
        position: relative;
        color: white;
        

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
    <BoardHelp show={showHelp} />
    <LineContainer active={true} text={' '+input} />
        
    <HiddenForm handleSubmit={handleSubmit} changeDisplay={changeDisplay} bind:value={input}/>
</div>  