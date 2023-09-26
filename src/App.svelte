<script lang="ts">
  import WebsiteTitle from "./lib/components/WebsiteTitle.svelte";
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
    <NavigationBar />
    <br />
    <br />
    <br />

    <p>
      {#if site == "links"}
        <Links />
      {:else if site == "blog"}
        <WebsiteTitle
          title="News, Auftritte und Blog"
          visible={true}
          size={1}
        />
        <Blog />
      {:else if site == "contact"}
        <Contact />
      {:else}
        <WebsiteTitle title="DJ und Producer" visible={true} size={1} />
        <WebsiteTitle
          title="Deep House - Progressive House - Tech House"
          visible={true}
          size={1}
        />

        <div class="gfg">
          <img src="robert.jpg" alt="" />
          <div class="text-container">
            <h1
              style="font-family: 'Times New Roman', Times, serif; font-size:xx-large"
            >
              DJ Robert Lenz
            </h1>
          </div>
        </div>
      {/if}
    </p>
  {:else}
    <h1>Die Website ist zurzeit Offline!</h1>
  {/if}
</main>
