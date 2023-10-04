<script lang="ts">
    import {Router, Link, Route} from "svelte-routing";

    import Home from "./lib/pages/Home.svelte";
    import About from "./lib/pages/about/About.svelte";
    import Links from "./lib/pages/links/Links.svelte";
    import Contact from "./lib/pages/contact/Contact.svelte";
    import Blog from "./lib/pages/blog/Blog.svelte";
    import type { SvelteComponent } from "svelte";

    export let url: string = "";

    interface NavBarLink {
        text: string;
        url: string;
        tooltip: string;
        component: typeof SvelteComponent<any>;
    }

    let links: NavBarLink[] = [];

    links.push({text: "Startseite", url: "/", tooltip: "Zur Startseite", component: Home});
    links.push({text: "Über Mich", url: "/about", tooltip: "Über Mich", component: About});
    links.push({text: "Blog", url: "/blog", tooltip: "", component: Blog});
    links.push({text: "Links", url: "/links", tooltip: "Lese den Blog", component: Links});
    links.push({text: "Kontakt", url: "/contact", tooltip: "Kantaktaufnahme", component: Contact});
</script>

<main>
    {#if links.length == 0}
        :C
    {/if}

    <Router {url}>
        <nav title="Navigiere durch die Website">


            {#each links as linkf, index}
                <Link to="{linkf.url}" title={linkf.tooltip}>
                    {linkf.text}
                </Link>
                {#if index != links.length - 1}
                |
                {/if}
            {/each}
        </nav>
        <hr>
        <br>
        <div>
            {#each links as linkf}
            <Route path={linkf.url} component={linkf.component}></Route>
            {/each}
        </div>
    </Router>
</main>