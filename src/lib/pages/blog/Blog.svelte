<script lang="ts">
    interface BlogEntry {
        name: string;
        content: string[];
        id : number;
    }

    let entries: BlogEntry[] = [];

    // add entries here:

    // loading all?
    let loadAll = false;

    // get id for loading a specific one
    let urlParams = new URLSearchParams(window.location.search);
    let id = urlParams.get("id");

    if (id === "" || id == null)
    {
        loadAll = true;
    }
</script>

<div>
    <h1 class="siteheader">Blog</h1>
    {#if entries.length === 0}
        <h2 class="sitesubheader">Zurzeit gibt es keine Einträge.</h2>
    {/if}
    {#each entries as entry}
        {#if (loadAll)}

        <a href="/blog/?id={entry.id}">
            <div>
                <h1 style="font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;">{entry.name}</h1>
                <div>
                    {#each entry.content as content}
                        <h2 style="color:antiquewhite; font-size: xx-larger">{content}</h2>
                    {/each}
                </div>
            </div>
        </a>
        {#if entries.length > 1}
            {#if entry !== entries[entries.length - 1]}
                <hr>
            {/if}
        {/if}
        {:else}
            {#if (entry.id.toString() === id)}
                <a href="/blog">Zurück.</a>
                <div>
                    <h1 style="font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif; font-size: 100px">{entry.name}</h1>
                    <div>
                        {#each entry.content as content}
                            <h1 style="color:antiquewhite; font-size: xx-larger">{content}</h1>
                        {/each}
                    </div>
                </div>
            {/if}
        {/if}

    {/each}
</div>
