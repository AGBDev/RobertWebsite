<script lang="ts">

    interface BlogEntry {
        name: string;
        content: string[];
    }

    let entries: BlogEntry[] = [];

</script>

<div>
    <div>
        {#each entries as entry}
            <h2>{entry.name}</h2>
            <h3>{entry.content}</h3>
        {/each}
    </div>
</div>
