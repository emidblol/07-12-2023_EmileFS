<script>
    import Strip from "./v2e.svelte";
    var airport = new URLSearchParams(window.location.search).get("ICAO");
    console.log(airport)
    if (airport == undefined) {
        airport = "EBBR";
    }
    function filter(arr) {
        return arr.filter(
            (item) =>
                item.flight_plan != null &&
                (item.flight_plan.arrival == airport.toUpperCase() ||
                    item.flight_plan.departure == airport.toUpperCase() ),
        );
    }
    async function awyep() {
        const res = await fetch("https://data.vatsim.net/v3/vatsim-data.json");
        const data = await res.json();
        //cut half of the pilot data
        var flightstoEBBR = filter(data.pilots);
        console.log("IMDONE")
        return flightstoEBBR;
    }
    let promise = awyep();
</script>

<link rel="stylesheet" href="styles.css" />
<div class="stripshelfv2">
    {#await promise then flights}
        worked
        {#each flights as flight}
            <Strip stripinf={flight} />
        {/each}
    {/await}
</div>
