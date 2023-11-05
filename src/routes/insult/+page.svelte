5:35
<title>Insult Fight - blazeannison</title>

<script lang="ts">

    let insultlist:string[] = [
        "I've meet pigs better at fighting then you.",
        "My great deeds are talked about across the land!",
        "I'm the greatest fighter on the seas!",
        "Out of breath already?",
        "Your mother.",
        "No one has ever faced me and lived!"
    ]
    let retortlsit:string[] = [
        "Glad to hear you're still in touch with your parents",
        "Well, everyones loves a good joke.",
        "Too bad you're facing me on dry land.",
        "Only from laughing at you!",
        "Your father",
        "With that bad breath, I'm not suprised."
    ]
    let names = [
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
    let current1:string[] = []
    let current2:string[] = []
    let current3:string[] = []
    let name = ""
    function resetrng() {
        current1 = []
        current2 = []
        current3 = []
        name = ""
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
        console.log(current1)
        console.log(current2)
        console.log(current3)
        let idx2 = Math.floor(Math.random() * names.length)
        name = names[idx2]
        console.log(name)
    }
    var play = false
    function playbutton() {
        play = true
    }
    if (play) {
        resetrng
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
        <img src="https://cdnb.artstation.com/p/assets/images/images/053/188/547/original/matthew-mai-sword-fight-study.gif?1661627203" alt="" id="fightingimg">
    {:else}
        <button on:click={playbutton}>Play!</button>
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
    }

    body {
        background-color: black;
        color: white;
    }
    button {
        border: 1px solid goldenrod;
        padding: 2%;
    }
</style>