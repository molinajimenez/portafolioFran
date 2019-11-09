<script>
    getInput=(e)=>{
        const { Onchange } = this.props
        const hiddenInput =  document.querySelector('input[name="inputConsole"]')
        if(e.which != 13){
            Onchange(hiddenInput.value)
        } else{
            //limpiamos input, limpiamos screen value
            Onchange('')
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


<form method="post" class="InputForm" autoComplete="off" onSubmit={this.handleSubmit}>
    <input autoComplete="off" name="inputConsole" onKeyUp={this.getInput}>
</form>