<script>
    let activate = false;

    function handleClick(){
       activate = !activate;
    }

</script>

<style>
    :global(body){
        background: #374046;
    }
    section{
        width: 100%;
        height: 1vh;
        margin: 0;
        padding: 0;
        transition: all 1s cubic-bezier(.5, -0.005, 0.2, 1);
        color: #fff;
        background: #374046;
        overflow: hidden;
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
        <a href="#t1"><i class="la la-male"></i></a>
        <a href="/terminal"><i class="la la-terminal"></i></a>
        <a href="#t1"><i class="la la-university"></i></a>
        <a href="#t1"><i class="la la-puzzle-piece"></i></a>
    </ul>
