<script lang="ts">
    import {Router, Link, Route} from "svelte-routing";

    import Home from "./lib/pages/Home.svelte";
    import About from "./lib/pages/about/About.svelte";
    import Links from "./lib/pages/links/Links.svelte";
    import Contact from "./lib/pages/contact/Contact.svelte";
    import Blog from "./lib/pages/blog/Blog.svelte";

    export let url: string = "";
</script>

<main>
    <Router {url}>
        <nav title="Navigiere durch die Website">
            <Link to="/" title="Wechsle zu der Startseite">Startseite</Link>
            |
<!--            <Link to="/about">Über Mich</Link>-->
<!--            |-->
            <Link to="/blog" title="Wechsle zum Blog">Blog</Link>
            |
            <Link to="/links" title="Wechsle zu den Links">Links</Link>
            |
            <Link to="/contact" title="Wechsle zu der Kontaktseite">Kontakt</Link>
        </nav>
        <hr>
        <br>
        <div>
            <Route path="/about" component={About}></Route>
            <Route path="/blog" component={Blog}></Route>
            <Route path="/links" component={Links}></Route>
            <Route path="/contact" component={Contact}></Route>
            <Route path="/" component={Home}></Route>
        </div>
    </Router>
</main>