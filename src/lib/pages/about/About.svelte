<script lang="ts">
    let lines: string[] = [];

    lines.push("Hi!");
    lines.push("Ich bin DJ Robert Lenz");
</script>

<div>
    <h1 class="siteheader">Über mich</h1>
    <div class="gfg">
    <img src="robert.jpg" alt=""  width="100%"  style="border-style: groove; border-color: #4a724b">
    <div class="text-container">
        <h2 style="font-family: 'Times New Roman', Times, serif;">DJ Robert Lenz</h2>
            <p style="font-family: 'Times New Roman', Times, serif;">DJ und Producer</p>
        </div>
    </div>
    <p>
        {#each lines as line}
            <h2 class="sitesubheader">{line}</h2>
        {/each}
    </p>
</div>