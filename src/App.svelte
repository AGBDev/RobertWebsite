<script lang="ts">
  import WebsiteTitle from "./lib/WebsiteTitle.svelte";
  import Blog from "./lib/blog/Blog.svelte";
    import TopBar from "./lib/topbar/TopBar.svelte";

  import {performance, PerformanceObserver} from 'perf_hooks';
</script>

<main>

  <TopBar></TopBar>

  <WebsiteTitle title="Robert Lennartz" visible={true} size={1} />
  <WebsiteTitle title="DJ und Musiker" visible={true} size={2}></WebsiteTitle>

  <img src="robert_logo_1.png" alt="">

  <br>
  <br>
  <WebsiteTitle  title="News, Auftritte und Blog" visible={true} size={2}></WebsiteTitle>

  <Blog></Blog>
  
</main>
