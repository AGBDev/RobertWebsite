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

    var isMobile = false; //initiate as false
    // device detection
    if(/(android|bb\d+|meego).+mobile|avantgo|bada\/|blackberry|blazer|compal|elaine|fennec|hiptop|iemobile|ip(hone|od)|ipad|iris|kindle|Android|Silk|lge |maemo|midp|mmp|netfront|opera m(ob|in)i|palm( os)?|phone|p(ixi|re)\/|plucker|pocket|psp|series(4|6)0|symbian|treo|up\.(browser|link)|vodafone|wap|windows (ce|phone)|xda|xiino/i.test(navigator.userAgent) 
        || /1207|6310|6590|3gso|4thp|50[1-6]i|770s|802s|a wa|abac|ac(er|oo|s\-)|ai(ko|rn)|al(av|ca|co)|amoi|an(ex|ny|yw)|aptu|ar(ch|go)|as(te|us)|attw|au(di|\-m|r |s )|avan|be(ck|ll|nq)|bi(lb|rd)|bl(ac|az)|br(e|v)w|bumb|bw\-(n|u)|c55\/|capi|ccwa|cdm\-|cell|chtm|cldc|cmd\-|co(mp|nd)|craw|da(it|ll|ng)|dbte|dc\-s|devi|dica|dmob|do(c|p)o|ds(12|\-d)|el(49|ai)|em(l2|ul)|er(ic|k0)|esl8|ez([4-7]0|os|wa|ze)|fetc|fly(\-|_)|g1 u|g560|gene|gf\-5|g\-mo|go(\.w|od)|gr(ad|un)|haie|hcit|hd\-(m|p|t)|hei\-|hi(pt|ta)|hp( i|ip)|hs\-c|ht(c(\-| |_|a|g|p|s|t)|tp)|hu(aw|tc)|i\-(20|go|ma)|i230|iac( |\-|\/)|ibro|idea|ig01|ikom|im1k|inno|ipaq|iris|ja(t|v)a|jbro|jemu|jigs|kddi|keji|kgt( |\/)|klon|kpt |kwc\-|kyo(c|k)|le(no|xi)|lg( g|\/(k|l|u)|50|54|\-[a-w])|libw|lynx|m1\-w|m3ga|m50\/|ma(te|ui|xo)|mc(01|21|ca)|m\-cr|me(rc|ri)|mi(o8|oa|ts)|mmef|mo(01|02|bi|de|do|t(\-| |o|v)|zz)|mt(50|p1|v )|mwbp|mywa|n10[0-2]|n20[2-3]|n30(0|2)|n50(0|2|5)|n7(0(0|1)|10)|ne((c|m)\-|on|tf|wf|wg|wt)|nok(6|i)|nzph|o2im|op(ti|wv)|oran|owg1|p800|pan(a|d|t)|pdxg|pg(13|\-([1-8]|c))|phil|pire|pl(ay|uc)|pn\-2|po(ck|rt|se)|prox|psio|pt\-g|qa\-a|qc(07|12|21|32|60|\-[2-7]|i\-)|qtek|r380|r600|raks|rim9|ro(ve|zo)|s55\/|sa(ge|ma|mm|ms|ny|va)|sc(01|h\-|oo|p\-)|sdk\/|se(c(\-|0|1)|47|mc|nd|ri)|sgh\-|shar|sie(\-|m)|sk\-0|sl(45|id)|sm(al|ar|b3|it|t5)|so(ft|ny)|sp(01|h\-|v\-|v )|sy(01|mb)|t2(18|50)|t6(00|10|18)|ta(gt|lk)|tcl\-|tdg\-|tel(i|m)|tim\-|t\-mo|to(pl|sh)|ts(70|m\-|m3|m5)|tx\-9|up(\.b|g1|si)|utst|v400|v750|veri|vi(rg|te)|vk(40|5[0-3]|\-v)|vm40|voda|vulc|vx(52|53|60|61|70|80|81|83|85|98)|w3c(\-| )|webc|whit|wi(g |nc|nw)|wmlb|wonu|x700|yas\-|your|zeto|zte\-/i.test(navigator.userAgent.substr(0,4))) { 
        isMobile = true;
    }

</script>

<!-- Uses a transparent header that draws on top of the layout's background -->
<style>
    .demo-layout-transparent {
      background: url('../assets/demos/transparent.jpg') center / cover;
    }
    .demo-layout-transparent .mdl-layout__header,
    .demo-layout-transparent .mdl-layout__drawer-button {
      /* This background is dark, so we set text to white. Use 87% black instead if
         your background is light. */
      color: white;
    }
    </style>


<!-- Always shows a header, even in smaller screens. -->
<div class="mdl-layout mdl-js-layout mdl-layout--fixed-header">
    <header class="mdl-layout__header">
      <div class="mdl-layout__header-row" style="background-color: black;">
        <!-- Title -->
        <span class="mdl-layout-title" style="background-color: black;">DJ Robert Lenz</span>
        <!-- Add spacer, to align navigation to the right -->
        <div class="mdl-layout-spacer" style="background-color: black;"></div>
        <!-- Navigation. We hide it in small screens. -->
        <nav class="mdl-navigation mdl-layout--large-screen-only" style="background-color: black;">
          <a class="mdl-navigation__link" href="/">Startseite</a>
          <a class="mdl-navigation__link" href="/about">Über</a>
          <a class="mdl-navigation__link" href="/links">Links</a>
          <a class="mdl-navigation__link" href="/contact">Kontakt</a>
        </nav>
      </div>
    </header>
    <div class="mdl-layout__drawer">
      <span class="mdl-layout-title">DJ Robert Lenz</span>
      <nav class="mdl-navigation">
        <a class="mdl-navigation__link" href="/">Startseite</a>
        <a class="mdl-navigation__link" href="/about">Über</a>
        <a class="mdl-navigation__link" href="/links">Links</a>
        <a class="mdl-navigation__link" href="/contact">Kontakt</a>
      </nav>
    </div>
  </div>

<main class="mdl-layout__content">
    <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
    <link rel="stylesheet" href="https://code.getmdl.io/1.3.0/material.indigo-pink.min.css">
    <script defer src="https://code.getmdl.io/1.3.0/material.min.js"></script>

    {#if links.length == 0}
        :C
    {/if}

    <Router {url}>
        <nav title="Navigiere durch die Website">
            {#each links as linkf, index}
                <Link to="{linkf.url}" title={linkf.tooltip}>
                    {linkf.text}
                </Link>
                {#if isMobile == true}
                <br>
                {:else}
                {#if index != links.length - 1}
                {"  |  "}
                {/if}
                {/if}
            {/each}
        </nav>
        <br>
        <div>
            {#each links as linkf}
                <Route path={linkf.url} component={linkf.component}></Route>
            {/each}
        </div>
    </Router>
</main>