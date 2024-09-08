<script lang="ts">
    interface BlogEntry {
        name: string;
        content: string;
        id : number;
        date: string;
        file: string;
    }

    let entries: BlogEntry[] = [];

    // add entries here:
    entries.push({name: "Änderungen der allgemeinen Geschäftsbedingungen", id: 0, content: 
        "Hallo! Ich bin ein Test-Blog! Ich habe darüber nachgedacht zu loolen.", 
        date: "05.10.23",
        file: "blogs/test.pdf"});

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
                <h3 >Veröffentlicht am {entry.date}</h3>
                <div>
                    <ul>
                        {#each entry.content.split("\n") as content, index}
                            {#if index < 2 && content.length < 40}
                                <p class="blogcontent">{content}</p>
                            {:else if index > 2}
                                <h2>...</h2>
                            {/if}
                        {/each}
                    </ul>
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
                    <!-- <h1 class="blogtitlebig">{entry.name}</h1>
                    <div>
                        {#each entry.content.split("\n") as content}
                            <h1 class="blogcontentbig">{content}</h1>
                        {/each}
                    </div> -->
                    <embed src="{entry.file}" type="application/pdf">
                </div>
            {/if}
        {/if}

    {/each}
</div>
