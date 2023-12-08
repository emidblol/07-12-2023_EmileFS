<script>
    import Strip from "./v2e.svelte";
    var airport = new URLSearchParams(window.location.search).get("ICAO");
    console.log(airport);
    if (airport == undefined) {
        airport = "EBBR";
    }
    function filter(arr) {
        return arr.filter(
            (item) =>
                item.flight_plan != null &&
                (item.flight_plan.arrival == airport.toUpperCase() ||
                    item.flight_plan.departure == airport.toUpperCase()),
        );
    }
    async function awyep() {
        const res = await fetch("https://data.vatsim.net/v3/vatsim-data.json");
        const data = await res.json();
        //cut half of the pilot data
        var flightstoEBBR = filter(data.pilots);
        console.log("IMDONE");
        return flightstoEBBR;
    }
    $: flights = [];
    let newFlights = [];
    let refresh = true;
    function checkForNewFlights() {
        // Replace this logic with your actual comparison logic
        awyep().then((newFlights) => {
            console.log(newFlights);
            
            //remove flights that are already in the list
            refresh = false;
            refresh = true;
            flights = newFlights;
        });
    }
    awyep().then((flightse) => {
        flights = flightse;
        setTimeout(checkForNewFlights, 2500);
    });
    // check if any new flights are added
</script>

<link rel="stylesheet" href="styles.css" />
<div class="stripshelfv2 abomination" dropzone="t">
    <h2>New cards</h2>
    {#key refresh}
        {#await awyep() then flights}
            {#each flights as flight}
                <Strip stripinf={flight} />
            {/each}
        {/await}
    {/key}
</div>
