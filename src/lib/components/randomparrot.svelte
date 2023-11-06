<script>
    let randomElement = ""
    let parrots = [
"deployparrot.gif",
"asyncparrot.gif",
"bananaparrot.gif",
"blondesassyparrot.gif",
"bluescluesparrot.gif",
"bobrossparrot.gif",
"chillparrot.gif",
"coffeeparrot.gif",
"cryptoparrot.gif",
"dabparrot.gif",
"darkbeerparrot.gif",
"databaseparrot.gif",
"dizzyparrot.gif",
"docparrot.gif",
"dreidelparrot.gif",
"drupal_parrot.gif",
"espressomartiniparrot.gif",
"ethparrot.gif",
"explodyparrot.gif",
"fadingparrot.gif",
"fidgetparrot.gif",
"fiestaparrot.gif",
"fixparrot.gif",
"halalparrot.gif",
"hamburgerparrot.gif",
"harrypotterparrot.gif",
"icecreamparrot.gif",
"krakenparrot.gif",
"loveparrot.gif",
"luckyparrot.gif",
"margaritaparrot.gif",
"matrixparrot.gif",
"mergedparrot.gif",
"metalparrot.gif",
"mongodbparrot.gif",
"oldtimeyparrot.gif",
"papalparrot.gif",
"parrot.gif",
"pear-parrots.gif",
"pizzaparrot.gif",
"portalparrot.gif",
"pythonparrot.gif",
"revertitparrot.gif",
"richpartyparrot.gif",
"rotatingparrot.gif",
"ryangoslingparrot.gif",
"schnitzelparrot.gif",
"shipitparrot.gif",
"shufflefurtherparrot.gif",
"shufflepartyparrot.gif",
"skiparrot.gif",
"slomoparrot.gif",
"sovjetparrot.gif",
"stalkerparrot.gif",
"standupparrot.gif",
"tacoparrot.gif",
"tripletsparrot.gif",
"uparrowparrot.gif",
"upvoteparrot.gif",
"wave1parrot.gif",
"wave2parrot.gif",
"wave3parrot.gif",
"wave4parrot.gif",
"wave5parrot.gif",
"wave6parrot.gif",
"wave7parrot.gif",
"wave8parrot.gif",
"wave9parrot.gif",
    ]
function generate() {
    randomElement = "https://cultofthepartyparrot.com/parrots/"+parrots[Math.floor(Math.random() * parrots.length)];
}
</script>
<body id="body">
    <button on:click={generate} id="generatebutton">Generate</button>
    <img src="{randomElement}" alt="pretend this is a party parrot" id="parrot">
</body>
<style>
    #generatebutton {
        border: 2px solid goldenrod;
        color: white;
        background-color: black;
        padding: 10px;
        width: fit-content;
    }
    #parrot {
        background-color: white;
        border: 2px solid goldenrod;
        padding: 10px;
        width: fit-content;
    }
    #body {
        display: flex;
        flex-direction: row;
    }
</style>