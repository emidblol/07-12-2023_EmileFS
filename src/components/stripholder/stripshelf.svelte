<script>
    import Strip from "../strips/index.svelte";
    // get props
    export let stripinf;
    console.log(stripinf);
</script>
<div>
{#each stripinf.stripinf as stri}
<!--{ wtc, nof, dep, cs, ssr, ew, e8, eRnav, eCPDLC, tn, des, rl }-->
    <Strip 
    wtc={stri.wtc}
    nof={stri.nof}
    dep={stri.dep}
    cs={stri.cs}
    ssr={stri.ssr}
    ew={stri.ew}
    e8={stri.e8}
    eRnav={stri.eRnav}
    eCPDLC={stri.eCPDLC}
    tn={stri.tn}
    des={stri.des}
    rl={stri.rl}
    style="width:50rem"
    />
{/each}
</div>