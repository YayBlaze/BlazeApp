<script lang="ts">
    export let choseninsult:string
    export var current1:string[]
    export var current2:string[]
    export var current3:string[]
    export let name:string
    export let health:number
    export let ophealth:number
    let correctretort:string = ""
    if (choseninsult != "") {
        if (choseninsult == current1[0]) {
            correctretort = current1[1]
            health -= 5
        }
        else if (choseninsult == current2[0]) {
            correctretort = current2[1]
            health -= 5
        }
        else if (choseninsult == current3[0]) {
            correctretort = current3[1]
            health -= 5
        }
        else {
            ophealth -= 5
        }
    }
    console.log(health)
    console.log(ophealth)
</script>


<body id="body">
    {#if (choseninsult != "")}
        <p>You say: <b>{choseninsult}</b></p>
        {#if correctretort != ""}
            <p>{name} says: <b>{correctretort}</b></p>
            <strong style="color: maroon;">Oof!</strong><p>That is the correct retort! You take 5 damage.</p>
        {:else}
            <p>{name} says: <b>Uhhh... yeah, so?</b></p>
            <p>That is not the correct retort! <b>{name} takes 5 damage.</b></p>
        {/if}
    {/if}
</body>


<style>
    #body {
        color: black;
        background-color: dimgray;
        border: 2px solid grey;
        border-radius: 12px;
        padding: 2%;
        width: 95%;
        height: fit-content;
        position: absolute;
        top: 70%;
        left: 0.5%;
    }
</style>