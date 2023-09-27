<script lang="ts">
    interface BlogEntry {
        name: string;
        content: string[];
        images: string[];
    }

    let entries: BlogEntry[] = [];

    entries.push({
        name: "Neuigkeiten zum 24.09.2023",
        content: [
            "Es gibt nun eine offizielle Website für DJ Robert Lenz.",
            "Auf dieser Website können sich Fans von Musik über Auftritte, Neuigkeiten und mehr informieren."],
        images: ["robert.jpg"]
    });

</script>

<div>
    {#each entries as entry}
        <div>
            <h1 style="font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;">{entry.name}</h1>
            <div>
                {#each entry.images as image}
                    <img src={image} alt="">
                {/each}
                {#each entry.content as content}
                    <h2 style="color:antiquewhite; font-size: xx-larger">{content}</h2>
                {/each}
            </div>
        </div>
    {/each}
</div>
