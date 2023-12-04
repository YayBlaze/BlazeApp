<title>Blaze's Website</title>

<script>

</script>

<nav id="nav">
    <h1 style="padding-right: 10%;">Home</h1>
    <div id="flex">
        <div id="gamesdropdown">
            <button class="gamesddbtn">Games</button>
            <div class="gamesddcontent">
                <a href="/insult">Insult Game</a>
                <a href="https://replit.com/@BlazeAnnison/Blazes-Game-Compond" target="_blank">Python Games</a>
            </div>
        </div>
        <a href="/parrot" style="padding-left: 10%;">Party Parrot o.o</a>
    </div>
</nav>


<p></p>


<body id="body">
    <h1>LOOK I CHANGED SOMETHING</h1>
</body>

<style>
    #body {
        color: white;
        background-color: black;
    }

    #nav {
        color: black;
        background-color: cornflowerblue;
        width: fit-content;
        padding: 10px 100% 10px 10px;
        display: flex;
    }

    #flex {
        display: flex;
        flex-direction: row;
        align-content: flex-end;
        text-align: end;
        width: fit-content;
    }
    .gamesddbtn {
        color: cornflowerblue;
        background-color: black;
        border-radius: 5px;
        padding: 10% ;
        height: fit-content;
        width: fit-content;
        border-style: hidden;
        transition: all 500ms;
    }
    .gamesddcontent {
        display: none;
        background-color: black;
        border: 1px solid dimgray;
        border-radius: 5px;
        color: cornflowerblue;
        padding: 10%;
        width: fit-content;
        height: fit-content;
        color: cornflowerblue;
        transition: 100ms;
    }
    .gamesddcontent a:hover{
        background-color: cornflowerblue;
        color: black;
    }
    .gamesddbtn:hover {
        background-color: dimgray;
        color: cornflowerblue;
    }
    #gamesdropdown:hover .gamesddcontent {
        display: block;
        color: cornflowerblue;
    }
</style>