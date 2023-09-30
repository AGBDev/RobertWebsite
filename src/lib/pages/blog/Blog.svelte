<script lang="ts">
    interface BlogEntry {
        name: string;
        content: string[];
        id : number;
    }

    let entries: BlogEntry[] = [];

</script>

<div>
    <h1 style="font-family: 'Times New Roman'">Blog</h1>
    {#each entries as entry}
        <div>
            <h1 style="font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;">{entry.name}</h1>
            <div>
                {#each entry.content as content}
                    <h2 style="color:antiquewhite; font-size: xx-larger">{content}</h2>
                {/each}
            </div>
        </div>
        {#if entries.length > 1}
            {#if entry !== entries[entries.length - 1]}
                <hr>
            {/if}
        {/if}
    {/each}
    {#if entries.length === 0}
        <h2 style="font-family: 'Times New Roman', Times, serif">Zurzeit gibt es keine Einträge.</h2>
    {/if}
</div>
