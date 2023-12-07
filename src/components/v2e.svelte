<script>
    export let stripinf;
    let stripinfo = stripinf;
    console.log(stripinfo);
    let a = 100;
</script>

<div class="stripparent" style="order: {a};">
    <input
        type="number"
        bind:value={a}
        style="width:5%; background-color:#7a0000; color:white;"
        class="stripinput"
    />
    <div class="strip" >
        <div style="grid-area: finf;" class="stripflex">
            <p>{stripinfo.flight_plan.callsign}</p>
            <p>{stripinfo.flight_plan.aircraft_short}</p>
            <p>{stripinfo.CID}</p>
        </div>
        <div style="grid-area: squawk;">
            {stripinfo.flight_plan.assigned_transponder}
        </div>
        <div style="grid-area: dest;">{stripinfo.flight_plan.arrival}</div>
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

<style>
    /* Chrome, Safari, Edge, Opera */
    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }

    /* Firefox */
    input[type="number"] {
        -moz-appearance: textfield;
        appearance: textfield;
    }
    .strip {
        display: grid;
        grid-template:
            "finf squawk dest route route route route" 40px
            "finf aFL   dest route route route route" 40px
            "finf rFL   dest route route route route" 40px / 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        background-color: #ffffff;
        width: 95%;
    }
    .stripparent {
        display: flex;
        justify-content: center;
        background-color: #7a0000;
        border: 1px solid black;
        width: 100%;
    }
    .strip div {
        border: 1px solid black;
    }
    .stripflex {
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
</style>
