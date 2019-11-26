<script>
    let activate = false;
    export let 
        isTerminal = false,
		isHobby = false,
		isMe = true, //this should be our landing...
		isEducation = false;

    function handleClick(){
       activate = !activate;
    }

    function activateTerminal(){         
        isTerminal = true;
        isMe = false;
        isEducation = false;
        isHobby = false;        
    }

    function activateMe(){         
        isTerminal = false;
        isMe = true;
        isEducation = false;
        isHobby = false;        
    }

    function activateEducation(){         
        isTerminal = false;
        isMe = false;
        isEducation = true;
        isHobby = false;        
    }

    function activateHobby(){
        isTerminal = false;
        isMe = false;
        isEducation = false;
        isHobby = true;      
    }

</script>

<style>
    :global(body){
        background: #374046;
    }
    

    ul {

        display: flex;
        flex-direction: column;
        align-items: center;
        position: fixed;
        top: 0;
        bottom: 0;
        left: 0;
        /*right: 0;*/
        margin: 0;
        margin-top: 10%;
        height: 95vh;
        max-width: 300px;
        width: 12vw;
        padding: 0;
        text-align: center;
        list-style-type: none;
        background: #c0def1;
    }
ul.controller{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    background: #374046;
    max-height: 21.4vh;
    margin: 0;
    margin-bottom: 5%;
    transition: 0.5s background ease-in;
}

ul.Activecontroller{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    background: #374046;
    max-height: 21.4vh;
    margin: 0;
    transition: 0.2s background ease-in;
    
}

ul > li:first-child{
    margin-top: 0;
}

ul > li:last-child{
    margin-bottom: 0;
}

ul.controller a{
    margin-bottom: 100%;
    color: white;
    font-size: 54px;
    margin:0;
    margin-top: 10%;
    margin-bottom: 5%;
    max-height: 64px;
    
}

ul.controller a i{
    transition: 0.45s transform ease-in-out; 
}

ul.Activecontroller a i{
    transform: rotate(180deg);
    transition: 0.45s transform ease-in-out; 
}

ul.Activecontroller a{
    margin-bottom: 100%;
    color: white;
    font-size: 54px;
    margin:0;
    margin-top: 10%;
    margin-bottom: 5%;
    max-height: 64px;
    
}
ul a {
    margin: 45px 0;
    list-style-type: none;
    display: block;
    
}

a {
    text-decoration: none;
    font-family: open sans, sans-serif;
}
a i{
    font-size: 54px;
}

ul.sideNav{
    left: -12vw;
    transition: 0.5s left ease-in;
    
}

ul.ActivesideNav{
    left: 0;
    transition: 0.5s left ease-in;
}

ul.ActivesideNav a i:hover{
    color: #f0134d;
    transition: 0.2s color ease-in-out;
}


</style>

    <ul class='{activate ? "Activecontroller" : "controller" }'>
        <a id="uniqueHamburguer" href="#t1"><i  class="la la-bars" on:click={handleClick}></i></a>
    </ul>
    
    <ul class='{activate ? "ActivesideNav" : "sideNav"}'>
        <a href="/#"><i class="la la-male" on:click={activateMe()}></i></a>
        <a href="/#"><i class="la la-terminal" on:click={activateTerminal()}></i></a>
        <a href="/#"><i class="la la-university" on:click={activateEducation()}></i></a>
        <a href="/#"><i class="la la-puzzle-piece" on:click={activateHobby()}></i></a>
    </ul>
