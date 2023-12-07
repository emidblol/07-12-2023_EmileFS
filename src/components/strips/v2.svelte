<script>
    export let stripinf;
    let stripinfo = stripinf.v2inf;
    console.log(stripinfo);
    // cs aInf CID ssr des rFL
</script>

<div class="stripparent">
    <div class="strip">
        <div style="grid-area: finf;" class="stripflex">
            <p>{stripinfo.cs}</p>
            <p>{stripinfo.aInf}</p>
            <p>{stripinfo.CID}</p>
        </div>
        <div style="grid-area: squawk;">{stripinfo.ssr}</div>
        <div style="grid-area: dest;">{stripinfo.des}</div>
        <div style="grid-area: route;">{stripinfo.route}</div>
        <div style="grid-area: aFL;">
            <input type="text" value="FL050" />
        </div>
        <div style="grid-area: rFL;">
            {stripinfo.rFL}
        </div>
    </div>
</div>

<style>
    .strip {
        display: grid;
        grid-template:
            "finf squawk dest route route route route" 40px
            "finf aFL   dest route route route route" 40px
            "finf rFL   dest route route route route" 40px / 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        background-color: #FFFFFF;
        width:100%;
    }
    .stripparent {
        display: flex;
        justify-content: center;
        background-color: #7a0000;
        padding-left: 10px;
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
