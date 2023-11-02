<title>Insult Fight - blazeannison</title>

<script lang="ts">
    let insultlist = [
        "I've meet pigs better at fighting then you.",
        "My great deeds are talked about across the land!",
        "I'm the greatest fighter on the seas!",
        "Out of breath already?",
        "Your mother.",
        "No one has ever faced me and lived!"
    ]
    let retortlsit = [
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
    function resetrng() {
        for (let i = 0; i < 4; i++) {
           let idx = Math.floor(Math.random() * 8)
           let insult = insultlist[idx]
           let retort = retortlsit[idx]
           if (i == 0) {
            current1.push(insult, retort)
           }
           else if (i == 1) {
            current2.push(insult, retort)
           }
           else if (i == 2) {
            current3.push(insult, retort)
           }
        }
        console.log(current1)
        console.log(current2)
        console.log(current3)
    }
</script>


<nav id="nav" class="hi">
    <p>Insult Fight Game</p>
    <a href="/">Back</a>
</nav>
 
<body id="body">
    <h2>Welcome to</h2>
    <h1>Insult Fight Game</h1>
    <button on:click={resetrng}>Button</button>
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

    #body {
        background-color: black;
        color: white;
    }
</style>