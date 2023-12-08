<script>
    export let stripinf;
    let stripinfo = stripinf;
    console.log(stripinfo);
    let a = 100;
    var airport = new URLSearchParams(window.location.search).get("ICAO");
    console.log(airport);
    if (airport == undefined) {
        airport = "EBBR";
    }

    function drag(ev) {
        ev.dataTransfer.setData("text", ev.target.id);
    }
</script>

<link rel="stylesheet" href="styles.css" />
{#if stripinfo.flight_plan.arrival == airport.toUpperCase()}
    <div
        class="stripparent"
        style="order: {a}; background-color:#7a0000;"
        draggable="true"
        ondragstart={drag}
        role="main"
        id="strip{stripinfo.cid}"
    >
        <div class="strip">
            <div style="grid-area: finf;" class="stripflex">
                <p>{stripinfo.callsign}</p>
                <p>{stripinfo.flight_plan.aircraft_short}</p>
                <p>{stripinfo.cid}</p>
            </div>
            <div style="grid-area: squawk;">
                {stripinfo.flight_plan.assigned_transponder}
            </div>
            <div style="grid-area: dest;">
                {stripinfo.flight_plan.departure}
            </div>
            <div
                style="grid-area: route; font-size:10px; overflow: hidden; text-overflow: ellipsis;"
            >
                {stripinfo.flight_plan.route}
            </div>
            <div style="grid-area: aFL;">
                <input type="text" value="FL050" />
            </div>
            <div style="grid-area: rFL;">
                {stripinfo.flight_plan.altitude}
            </div>
        </div>
    </div>
{:else}
    <div
        class="stripparent"
        style="order: {a}; background-color:#006faf;"
        draggable="true"
        role="main"
        ondragstart={drag}
        id="strip{stripinfo.cid}"
    >
        <div class="strip">
            <div style="grid-area: finf;" class="stripflex">
                <p>{stripinfo.callsign}</p>
                <p>{stripinfo.flight_plan.aircraft_short}</p>
                <p>{stripinfo.cid}</p>
            </div>
            <div style="grid-area: squawk;">
                {stripinfo.flight_plan.assigned_transponder}
            </div>
            <div style="grid-area: dest;">
                {stripinfo.flight_plan.arrival}
            </div>
            <div
                style="grid-area: route; font-size:10px; overflow: hidden; text-overflow: ellipsis;"
            >
                {stripinfo.flight_plan.route}
            </div>
            <div style="grid-area: aFL;">
                <input type="text" value="FL050" />
            </div>
            <div style="grid-area: rFL;">
                {stripinfo.flight_plan.altitude}
            </div>
        </div>
    </div>
{/if}
