<script>


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
        margin-top: 7%;
        height: 95vh;
        max-width: 300px;
        width: 10%;
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
    max-height: fit-content;
    margin: 0;
    margin-bottom: 5%;
    
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


</style>
<section>
    <ul class="controller">
        <a id="uniqueHamburguer" href="#t1"><i  class="la la-bars"></i></a>
    </ul>
    
    <ul>
        <a href="#t1"><i class="la la-male"></i></a>
        <a href="#t1"><i class="la la-terminal"></i></a>
        <a href="#t1"><i class="la la-university"></i></a>
        <a href="#t1"><i class="la la-puzzle-piece"></i></a>
    </ul>
</section>
