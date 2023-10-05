<script lang="ts">
    interface BlogEntry {
        name: string;
        content: string[];
        id : number;
        date: string;
    }

    let entries: BlogEntry[] = [];

    // add entries here:
    entries.push({name: "Test", id: 0, content: [
        "Das ist ein TesT. Der ist ganz toll",
        "Er ist nicht besonders hilfreich, aber ok.",
        "f",
        "Shesh"
    ], date: "05.10.23"});

    entries.reverse();

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

        <a href="/blog/?id={entry.id}" >
            <div style="border-style: double;">
                <h1 class="blogtitle">{entry.name}</h1>
                <h2 >Veröffentlicht am {entry.date}</h2>
                <div>
                    {#each entry.content as content, index}
                        {#if index < 2 && content.length < 40}
                            <h2 class="blogcontent">{content}</h2>
                        {:else if index > 2}
                            <!-- <h2 class="blogcontent" style="border-style:double">Ganzen Eintrag sehen</h2> -->
                            <h2>...</h2>
                        {/if}
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
                <a href="/blog" style="font-size: 150%;">Zurück</a>
                <div>
                    <h1 class="blogtitlebig">{entry.name}</h1>
                    <div>
                        {#each entry.content as content}
                            <h1 class="blogcontentbig">{content}</h1>
                        {/each}
                    </div>
                </div>
            {/if}
        {/if}

    {/each}
</div>
