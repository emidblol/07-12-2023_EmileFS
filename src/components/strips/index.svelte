<script>
    export let wtc;
    export let nof;
    export let dep;
    export let cs;
    export let ssr;
    export let ew;
    export let e8;
    export let eRnav;
    export let eCPDLC;
    export let tn;
    export let des;
    export let rl;
</script>

<div class="strip">
    <div style="grid-area: wtc;">
        {wtc}
    </div>
    <div style="grid-area: nof;">
        {nof}
    </div>
    <div style="grid-area: dep;">
        {dep}
    </div>
    <div style="grid-area: rl;">
        {rl}
    </div>
    <div style="grid-area: cs;">
        {cs}
    </div>
    <div style="grid-area: ssr;">
        {ssr}
    </div>
    <div style="grid-area: ew;">
        {ew}
    </div>
    <div style="grid-area: e8;">
        {e8}
    </div>
    <div style="grid-area: eRnav;">
        {eRnav}
    </div>
    <div style="grid-area: eCPDLC;">
        {eCPDLC}
    </div>
    <div style="grid-area: tn;">
        {tn}
    </div>
    <div style="grid-area: des;">
        {des}
    </div>
    <div style="grid-area: x;"></div>
    <div style="grid-area: y;"></div>
    <div style="grid-area: z;"></div>
    <div style="grid-area: o;"></div>
    <div style="grid-area: xx;"></div>
    <div style="grid-area: yy;"></div>
    <div style="grid-area: zz;"></div>
</div>
<style>
    .strip {
        display: grid;
        grid-template:
            "wtc    wtc     wtc     wtc     nof     nof     nof     nof     dep     dep     dep     dep     rl  rl  rl  rl  x  x  x  x  y  y  y  y  z  z  z  z  o  o  o  o" 50px
            "cs     cs      cs      cs      cs      cs      cs      cs      ssr     ssr     ssr     ssr     rl  rl  rl  rl  x  x  x  x  y  y  y  y  z  z  z  z  o  o  o  o" 50px
            "ew     e8      eRnav   eCPDLC  tn      tn      tn      tn      des     des     des     des     rl  rl  rl  rl  xx xx xx xx yy yy yy yy zz zz zz zz o  o  o  o" 50px / 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        aspect-ratio: 1122/126;
    }
    .strip > div {
        background-color: #dde9f5;
        border: 1px solid #000;
        padding: 10px;
        font-size: 30px;
        text-align: center;
        user-select: none;
    }
</style>
