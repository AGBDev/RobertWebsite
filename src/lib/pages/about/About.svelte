<script lang="ts">
    let lines: string[] = [];

    lines.push("Soos");
    lines.push("Soos");
</script>


<div>
    <h1 class="siteheader">Über mich</h1>
    {#each lines as line}
        <h2 class="sitesubheader">{line}</h2>
    {/each}
    <!-- <h2 class="sitesubheader">
        Hallo, meine Name ist Robert Lenz.
    </h2>
    <h2 class="sitesubheader">
        Ich bin DJ und Producer aus dem Raum Aachen.
    </h2> -->
</div>