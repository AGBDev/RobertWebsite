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
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. At dolore expedita excepturi aliquid debitis libero vel obcaecati, optio voluptates voluptatum repellat provident sit quaerat repellendus. Eius voluptas ratione tenetur commodi..", 
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. At dolore expedita excepturi aliquid debitis libero vel obcaecati, optio voluptates voluptatum repellat provident sit quaerat repellendus. Eius voluptas ratione tenetur commodi.."], 
        images: []
    });
    

</script>


<div>
    {#each entries as entry, index}
        <div style="border-style:groove;">
            <h1 style="font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;">{entry.name}</h1>
            <div>
                {#each entry.images as image}
                    <img src={image} alt="">
                {/each}
                {#each entry.content as content}
                    <h2 style="color: beige; serif">{content}</h2>
                {/each}
            </div>
        </div>
    {/each}
</div>
