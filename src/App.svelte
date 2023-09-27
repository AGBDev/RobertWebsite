<script lang="ts">
    import Blog from "./lib/pages/blog/Blog.svelte";
    import NavigationBar from "./lib/components/navigationbar/NavigationBar.svelte";
    import Links from "./lib/pages/links/Links.svelte";
    import Contact from "./lib/pages/contact/Contact.svelte";

    const load = () => {
        const params = new URLSearchParams(document.location.search);

        const f = params.get("site");

        return f;
    };

    let site = load();

    // set to true to block access
    let block_access = false;
</script>

<main>
    {#if block_access == false}

        <NavigationBar/>

        {#if site == "links"}
            <Links/>
        {:else if site == "blog"}
            <h1>News, Auftritte und Blog</h1>
            <Blog/>
        {:else if site == "contact"}
            <Contact/>
        {:else}
            <h1 style="font-family: 'Times New Roman', Times, serif">DJ und Producer</h1>
            <h1 style="font-family: 'Times New Roman', Times, serif">Deep House - Progressive House - Tech House</h1>

            <div class="gfg">
                <img src="robert.jpg" alt=""/>
                <div class="text-container">
                    <h1
                            style="font-family: 'Times New Roman', Times, serif; font-size:xx-large"
                    >
                        DJ Robert Lenz
                    </h1>
                </div>
            </div>

            <div style="border-style: solid;">
                <h2 style="font-size: 40px; font-family:'Times New Roman', Times, serif">Über mich</h2>
                <h2 style="font-family: 'Times New Roman', Times, serif; font-size: 35px;">
                    Hallo, meine Name ist Robert Lenz.
                </h2>
                <h2 style="font-family: 'Times New Roman', Times, serif; font-size: 35px">
                    Ich bin DJ und Producer aus dem Raum Aachen.
                </h2>
            </div>

        {/if}
    {:else}
        <h1>error</h1>
    {/if}
</main>
