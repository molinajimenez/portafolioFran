<script>
    let value;
    export let input;
    export let handleSubmit;
    export let changeDisplay;
    function getInput(e){
        
        const hiddenInput = document.querySelector('input[name="inputConsole"]')
        if(e.which != 13){
           input = hiddenInput.value;
           changeDisplay(input);
        } else{
            //limpiamos input, limpiamos screen value
            input = "";
            changeDisplay("");
            hiddenInput.value = ''
        }
        
    }
</script>

<style>
    form.InputForm{
        position: absolute;
        left: 10px;
        z-index: -10;
    }
    input{
        font-size: 16px;
    }

</style>


<form method="post" class="InputForm" autoComplete="off" on:submit={handleSubmit}>
    <input autoComplete="off" name="inputConsole" on:keyup={getInput}>
</form>