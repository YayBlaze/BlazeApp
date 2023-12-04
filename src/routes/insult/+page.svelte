<title>Insult Fight - blazeannison</title>

<script lang="ts">
    import Insultstorybox from "$lib/components/insultstorybox.svelte";
    var play:boolean = false
    var health = 20
    var ophealth = 20
    var choseninsult:string = ""
    var insultlist:string[] = [
        "I've meet pigs better at fighting then you.",
        "My great deeds are talked about across the land!",
        "I'm the greatest fighter on the seas!",
        "Out of breath already?",
        "Your mother.",
        "No one has ever faced me and lived!"
    ]
    var retortlsit:string[] = [
        "Glad to hear you're still in touch with your parents",
        "Well, everyones loves a good joke.",
        "Too bad you're facing me on dry land.",
        "Only from laughing at you!",
        "Your father",
        "With that bad breath, I'm not suprised."
    ]
    var names:string[] = [
        "Tate the Great",
        "Rexydoodles",
        "Sword Loard Joe",
        "Mr. all good bob",
        "The Magic Man",
        "Dan the Library Man",
        "Your mother",
        "Blaze Annison",
        "Mr. Develepor",
        "Charlie - The Minecraft Nerd"
    ]
    var current1:string[] = []
    var current2:string[] = []
    var current3:string[] = []
    var name = ""
    function resetrng() {
        play = true
        current1 = []
        current2 = []
        current3 = []
        name = ""
        for (let i = 0; i < 4; i++) {
           let idx = Math.floor(Math.random() * insultlist.length)
           let insult = insultlist[idx]
           let retort = retortlsit[idx]
           if (i == 0) {
            current1.push(insult, retort)
            insultlist.splice(idx,1)
            retortlsit.splice(idx,1)
           }
           else if (i == 1) {
            current2.push(insult, retort)
            insultlist.splice(idx,1)
            retortlsit.splice(idx,1)
           }
           else if (i == 2) {
            current3.push(insult, retort)
            insultlist.splice(idx,1)
            retortlsit.splice(idx,1)
           }
        }
        insultlist = [
            "I've meet pigs better at fighting then you.",
            "My great deeds are talked about across the land!",
            "I'm the greatest fighter on the seas!",
            "Out of breath already?",
            "Your mother.",
            "No one has ever faced me and lived!"
        ]
        retortlsit = [
            "Glad to hear you're still in touch with your parents",
            "Well, everyones loves a good joke.",
            "Too bad you're facing me on dry land.",
            "Only from laughing at you!",
            "Your father",
            "With that bad breath, I'm not suprised."
        ]
        console.log(current1)
        console.log(current2)
        console.log(current3)
        let idx2 = Math.floor(Math.random() * names.length)
        name = names[idx2]
        console.log(name)
    }
    function attackation() {
        let rng = Math.floor(Math.random() * 10)
        console.log(rng)
        if (rng <= 5) {
            health -= 2
            ophealth -= 1
        }
        else {
            health -= 1
            ophealth -= 2
        }
    }
    var insulttoggle:boolean = false
    function insultaction() {
        insulttoggle = true
    }
    function chooseinsult(insultclicked:string) {
        choseninsult = insultclicked
    }
    function reset() {
        play = false
        health = 20
        ophealth = 20
    }
</script>


<nav id="nav" class="hi">
    <p>Insult Fight Game</p>
    <a href="/">Back</a>
</nav>

<body>
    <h2>Welcome to</h2>
    <h1>Insult Fight Game</h1>
    {#if play}
        <div id="stats">
            <div>
                <p><b>Your Oponent: </b>{name}</p>
                <p><b>Your Oponent's Health: </b>{ophealth}</p>
            </div>
            <div id="YoureStats">
                <p><b>Your Health: </b>{health}</p>
            </div>
        </div>
        <div id="choicebox">
            {#if (insulttoggle == false)}
                {#if health > 0}
                    {#if ophealth > 0}
                           <p>Would you like to</p>
                        <div style="display: flex;">
                            <button class="choice" on:click={attackation}>Attack</button>
                            <p>or</p>
                            <button class="choice" on:click={insultaction}>Insult</button>
                        </div>
                       {:else}
                        <h1 style="color: greenyellow;"><strong>You Win!</strong></h1>
                        <button id="greenbutton" on:click={reset}>Ok</button>
                    {/if}
                {:else}
                    <h1 style="color: red;"><strong>You Lose!</strong></h1>
                    <button id="redbutton" on:click={reset}>Ok</button>
                {/if}
                {:else}
                <p>Choose your insult:</p>
                <div class="flexcolumn">
                    {#each insultlist as insult}
                        <button id="insultchoice" on:click={chooseinsult(insult)}>{insult}</button>
                    {/each}
                </div>
            {/if}
        </div>
        <Insultstorybox choseninsult={choseninsult} current1={current1} current2={current2} current3={current3} name={name} health={health} ophealth={ophealth}></Insultstorybox>
    {:else}
        <button on:click={resetrng} id="plybutton">Play!</button>
    {/if}
</body>


<style>
    #nav {
        background-color: cornflowerblue;
        color: black;
        width: fit-content;
        padding: 10px 100% 10px 10px;
        display: flex;
        flex-direction: row;
        border-radius: 5px;
    }

    body {
        background-color: black;
        color: white;
    }
    #plybutton {
        border: 1px solid goldenrod;
        padding: 1%;
        background-color: black;
        color: white;
        border-radius: 5px;
        transition: all 500ms; 
    }
    #plybutton:hover {
        background-color: goldenrod;
        color: black;
    }
    #stats {
        display: flex;
        flex-direction: row;
        background-color: dimgray;
        border: 2px solid grey;
        padding: 1%;
        border-radius: 12px;
        color: black;
    }
    #YoureStats {
        text-align: right;
        position: absolute;
        right: 50%;
    }
    #choicebox {
        color: black;
        background-color: dimgray;
        border: 2px solid grey;
        border-radius: 12px;
        padding: 1%;
        width: 95%;
        height: fit-content;
        position: absolute;
        top: 45%;
    }
    .choice {
        height: fit-content;
        width: fit-content;
        padding: 1%;
        background-color: black;
        border: 1px solid goldenrod;
        border-radius: 5px;
        color: white;
        transition: all 500ms;
    }
    .choice:hover {
        background-color: goldenrod;
        color: black;
    }
    #insultchoice {
        border: 1px solid goldenrod;
        background-color: black;
        color: white;
        border-radius: 5px;
        width: fit-content;
        height: fit-content;
        transition: all 500ms;
    }
    #insultchoice:hover {
        border-radius: 5px;
        background-color: goldenrod;
        color: black;
    }
    .flexcolumn {
        display: flex;
        flex-direction: column;
        height: fit-content;
    }
    #redbutton {
        color: red;
        background-color: black;
        border: 1px solid red;
        border-radius: 5px;
        padding: 1%;
        transition: 200ms;
    }
    #redbutton:hover {
        background-color: red;
        color: black;
    }
    #greenbutton {
        color: greenyellow;
        background-color: black;
        border: 1px solid greenyellow;
        border-radius: 5px;
        padding: 1%;
        transition: 200ms;
    }
    #greenbutton:hover {
        background-color: greenyellow;
        color: black;
    }
</style>